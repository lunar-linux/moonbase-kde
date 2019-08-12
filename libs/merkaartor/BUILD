  . /etc/profile.d/qt5.rc &&

sed -i 's/GDAL_VERSION_MAJOR == 2/GDAL_VERSION_MAJOR == 3/' src/ImportExport/ImportExportGdal.h &&

# Spatialite is not working.
lrelease src/src.pro &&
/usr/lib/qt5/bin/qmake PREFIX=/usr     \
                       NODEBUG=1       \
                       QMAKE_CXXFLAGS="$CXXFLAGS -DACCEPT_USE_OF_DEPRECATED_PROJ_API_H=1" \
                       Merkaartor.pro $OPTS &&

default_make
