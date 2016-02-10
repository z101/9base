#!/bin/bash

maxpnum=
while [ "$1" != "" ]; do
	case $1 in
		[0-9]|[1-9][0-9] )
			maxpnum=$1
			;;
		* )
	esac
	shift
done
echo "param: max patch num = $maxpnum"
patches=($(eval "ls -1b | sort | grep 'patch\.[0-9][0-9]\.*' | head -$maxpnum"))
for f in "${patches[@]}"; do
	echo " - applying $f..."
	patch -p1 < $f
done
