```bash
##############################################################################################################################
# Message #
###########
echo "#################################";
echo "#       Patchage du Kernel      #";
echo "#################################";
echo "#                               #";
echo "# Kernel d'Originel : $(make kernelversion)    #";
echo "#                               #";
#
##############################################################################################################################
# Patch 6.10.1 #
################
#patch -p1 --batch --ignore-whitespace < ../patch-${KERNEL_MAJOR}.${KERNEL_MINOR}.1 1>/dev/null;
#echo "# Patch : $(make kernelversion)                #";
#sed -i -e "s/SUBLEVEL \= 1/SUBLEVEL \= 0/g" Makefile;
#
##############################################################################################################################
# Patch 6.10.2 #
################
#patch -p1 --batch --ignore-whitespace < ../patch-${KERNEL_MAJOR}.${KERNEL_MINOR}.2 1>/dev/null;
#echo "# Patch : $(make kernelversion)                #";
#sed -i -e "s/SUBLEVEL \= 2/SUBLEVEL \= 0/g" Makefile;
#
##############################################################################################################################
# Patch 6.10.3 #
################
#patch -p1 --batch --ignore-whitespace < ../patch-${KERNEL_MAJOR}.${KERNEL_MINOR}.3 1>/dev/null;
#echo "# Patch : $(make kernelversion)                #";
#sed -i -e "s/SUBLEVEL \= 3/SUBLEVEL \= 0/g" Makefile;
#
##############################################################################################################################
# Patch 6.10.4 #
################
#patch -p1 --batch --ignore-whitespace < ../patch-${KERNEL_MAJOR}.${KERNEL_MINOR}.4 1>/dev/null;
#echo "# Patch : $(make kernelversion)                #";
#sed -i -e "s/SUBLEVEL \= 4/SUBLEVEL \= 0/g" Makefile;
#
##############################################################################################################################
# Patch 6.10.5 #
################
#patch -p1 --batch --ignore-whitespace < ../patch-${KERNEL_MAJOR}.${KERNEL_MINOR}.5 1>/dev/null;
#echo "# Patch : $(make kernelversion)                #";
#sed -i -e "s/SUBLEVEL \= 5/SUBLEVEL \= 0/g" Makefile;
#
##############################################################################################################################
# Patch 6.10.6 #
################
#patch -p1 --batch --ignore-whitespace < ../patch-${KERNEL_MAJOR}.${KERNEL_MINOR}.6 1>/dev/null;
#echo "# Patch : $(make kernelversion)                #";
#sed -i -e "s/SUBLEVEL \= 6/SUBLEVEL \= 0/g" Makefile;
#
##############################################################################################################################
# Patch 6.10.7 #
################
#patch -p1 --batch --ignore-whitespace < ../patch-${KERNEL_MAJOR}.${KERNEL_MINOR}.7 1>/dev/null;
#echo "# Patch : $(make kernelversion)                #";
#sed -i -e "s/SUBLEVEL \= 7/SUBLEVEL \= 0/g" Makefile;
#
##############################################################################################################################
# Patch 6.10.8 #
################
#patch -p1 --batch --ignore-whitespace < ../patch-${KERNEL_MAJOR}.${KERNEL_MINOR}.8 1>/dev/null;
#echo "# Patch : $(make kernelversion)                #";
#sed -i -e "s/SUBLEVEL \= 8/SUBLEVEL \= 0/g" Makefile;
#
##############################################################################################################################
# Patch 6.10.9 #
################
#patch -p1 --batch --ignore-whitespace < ../patch-${KERNEL_MAJOR}.${KERNEL_MINOR}.9 1>/dev/null;
#echo "# Patch : $(make kernelversion)                #";
#sed -i -e "s/SUBLEVEL \= 9/SUBLEVEL \= 0/g" Makefile;
#
##############################################################################################################################
# Patch 6.10.10 #
#################
#patch -p1 --batch --ignore-whitespace < ../patch-${KERNEL_MAJOR}.${KERNEL_MINOR}.10 1>/dev/null;
#echo "# Patch : $(make kernelversion)               #";
#sed -i -e "s/SUBLEVEL \= 10/SUBLEVEL \= 0/g" Makefile;
#
##############################################################################################################################
# Patch 6.10.11 #
#################
#patch -p1 --batch --ignore-whitespace < ../patch-${KERNEL_MAJOR}.${KERNEL_MINOR}.11 1>/dev/null;
#echo "# Patch : $(make kernelversion)               #";
#sed -i -e "s/SUBLEVEL \= 11/SUBLEVEL \= 0/g" Makefile;
#
##############################################################################################################################
# Patch 6.10.12 #
#################
#patch -p1 --batch --ignore-whitespace < ../patch-${KERNEL_MAJOR}.${KERNEL_MINOR}.12 1>/dev/null;
#echo "# Patch : $(make kernelversion)               #";
#sed -i -e "s/SUBLEVEL \= 12/SUBLEVEL \= 0/g" Makefile;
#
##############################################################################################################################
# Patch 6.10.13 #
#################
#patch -p1 --batch --ignore-whitespace < ../patch-${KERNEL_MAJOR}.${KERNEL_MINOR}.13 1>/dev/null;
#echo "# Patch : $(make kernelversion)               #";
#sed -i -e "s/SUBLEVEL \= 13/SUBLEVEL \= 0/g" Makefile;
#
##############################################################################################################################
# Patch 6.10.14 #
#################
#patch -p1 --batch --ignore-whitespace < ../patch-${KERNEL_MAJOR}.${KERNEL_MINOR}.14 1>/dev/null;
#sed -i -e "s/SUBLEVEL \= 14/SUBLEVEL \= 0/g" Makefile;
#
##############################################################################################################################
echo "#                               #";
echo "# Final : $(make kernelversion)               #";
echo "#                               #";
echo "#################################";
echo "";
##############################################################################################################################
```
