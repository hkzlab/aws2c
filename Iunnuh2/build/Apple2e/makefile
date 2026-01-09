cc65_options = -O -C apple2enh-system.cfg -t apple2enh -D APPLE2E -D NCOL=80 -D CV_IS_A_FUNCTION 
output_dir = Apple2e_Iunnuh
aws_options  = -m -c -s -d -n -w -3 -kk -R res.lst mapfile.h

all: Apple2e

iunnuh2_no_utf8.c: ../../aws_sources/Iunnuh2Maledizione.AWS
	../../../aws2c $(aws_options) -f config_it_nu.h ../../aws_sources/Iunnuh2Maledizione.AWS iunnuh2_no_utf8.c

iunnuh2_no_utf8_en.c: ../../aws_sources/Iunnuh2TheCurse.AWS
	../../../aws2c $(aws_options) -f config_en_nu.h ../../aws_sources/Iunnuh2TheCurse.AWS iunnuh2_no_utf8_en.c


Apple2e: inout.c iunnuh2_no_utf8.c iunnuh2_no_utf8_en.c resource.c
	cl65  -DCONFIG_FILENAME=\"config_it_nu.h\" --mapfile iunnuh2e.map $(cc65_options) iunnuh2_no_utf8.c inout.c loadsave.c resource.c -o iunnuh2e_it
	cl65  -DCONFIG_FILENAME=\"config_en_nu.h\" --mapfile iunnuh2e.map $(cc65_options) iunnuh2_no_utf8_en.c inout.c loadsave.c resource.c -o iunnuh2e_en
	

clean:
	rm iunnuh2.c iunnuh2_it iunnuh2_no_utf8.c iunnuh2_en.c iunnuh2_en iunnuh2_it  iunnuh2_no_utf8_en.c iunnuh2_it_a iunnuh2_en_a config_it_nu.h config_en_nu.h iunnuh2e iunnuh2i *.o
