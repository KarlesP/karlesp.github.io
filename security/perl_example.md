---
layout: page
title: Example Code for Perl
---

## Example
```
#!/usr/bin/perl -w
use strict;
use Digest::SHA qw(sha1_hex);
sub passwd($$); # prototype
open(HSH,“hashes.txt”);
while(<HSH>){
chomp $_;
$_ =~ s/\s+//g; # remove all whitespace
my($hash,$user) = ””;
if(m/(.+):(.+)/){
$user = $1;
$hash = $2;
}
my $passwd = passwd($hash,$user);
print $passwd if($passwd !~ m/ot foun/);
}
sub passwd($$){
my $hash = shift;
my $user = shift;
open(WRD,“words.txt”);
while(<WRD>){
chomp $_;
if(sha1_hex($_) eq $hash){
close WRD;
return “Password: “.$_.” = “.$hash.” from User: “.$user.”\n”;
}
}
close WRD;
return “not found.”;
}
```
