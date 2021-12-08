  . /etc/profile.d/qt5.rc &&

sed -i 's/GDAL_VERSION_MAJOR == 2/GDAL_VERSION_MAJOR == 3/' src/ImportExport/ImportExportGdal.h &&

# Spatialite is not working.
lrelease src/src.pro &&
/usr/lib/qt5/bin/qmake PREFIX=/usr     \
                       NODEBUG=1       \
                       Merkaartor.pro $OPTS &&

default_make
