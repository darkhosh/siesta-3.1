# 
# This file is part of the SIESTA package.
#
# Copyright (c) Fundacion General Universidad Autonoma de Madrid:
# E.Artacho, J.Gale, A.Garcia, J.Junquera, P.Ordejon, D.Sanchez-Portal
# and J.M.Soler, 1996- .
# 
# Use of this software constitutes agreement with the full conditions
# given in the SIESTA license, as signed by all legitimate users.
#
#
# Makefile for LWF to netCDF converter
#
#  The arch.make file is supposed to be in $(OBJDIR). This is normally
#  the top Obj, but if you are using architecture-dependent build directories
#  you might want to change this. (If you do not understand this, you do not
#  need to change anything. Power users can do "make OBJDIR=Whatever".)
#
#  If your main Siesta build used an mpi compiler, you might need to
#  define an FC_SERIAL symbol in your top arch.make, to avoid linking
#  in the mpi libraries even if we explicitly undefine MPI below.
#
.SUFFIXES: 
.SUFFIXES: .f .F .o .a  .f90 .F90
#
default: lwf2cdf
all: lwf2cdf
#
OBJDIR=Obj
include ../../$(OBJDIR)/arch.make
#
# We assume that the top arch.make defines the relevant NetCDF symbols,
# including the INCFLAGS line. If not, uncomment the following lines, 
# using appropriate information
#
# NETCDF_ROOT=/some/path
# INCFLAGS=-I$(NETCDF_ROOT)/include
# NETCDF_LIBS=-L$(NETCDF_ROOT)/lib -lnetcdf
#
#
INCFLAGS:= $(NETCDF_INCFLAGS) $(INCFLAGS)
#
lwf2cdf: lwf2cdf.o
	$(FC) $(LDFLAGS) -o $@ lwf2cdf.o  $(NETCDF_LIBS)
#
clean: 
	rm -f *.o lwf2cdf  *.o *.*d
#





