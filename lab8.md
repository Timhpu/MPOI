**Lab 8**

1.
```r
install.packages("BiocManager")
BiocManager::install(version='devel')
BiocManager::install("rhdf5")
library('rhdf5')

h5file = H5Fcreate("newfile.h5")
h5group1 <-H5Gcreate(h5file, "foo")
h5group2 <-H5Gcreate(h5file, "baa")
h5group3 <-H5Gcreate(h5group1, "foobaa")
h5file
h5group3
```

2.
```r
d = c(3, 4)
h5space1 = H5Screate_simple(d,d)
h5space2 = H5Screate_simple(d,NULL)
h5space3 = H5Scopy(h5space1)
h5space4 = H5Screate("H5S_SCALAR")
h5space1

h5dataset1 = H5Dcreate(h5file, "dataset1", "H5T_IEEE_F32LE", h5space1)
H5Dwrite(h5dataset1, seq(0.2, 2.4, length.out=12))
h5dataset1

h5dataset2 = H5Dcreate(h5group2, "dataset2", "H5T_STD_I32LE", h5space3)
H5Dwrite(h5dataset2, 10:120)
h5dataset2

H5Fclose(h5file)

h5file1 <- H5Fopen("newfile.h5")
h5ls(h5file1)
H5Fclose(h5file1)
```

3.
```r
sessionInfo()
```
