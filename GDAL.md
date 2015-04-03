GDALのコマンドラインチートシート
===============================

* 画像のリサイズ（GeoTiffの画像サイズを変換）
```
gdal_translate -of "GTiff" -outsize 35% 35% image.tif image.tif
```

* 標高メッシュデータからポイント型のSHPファイルを作成（実際にはこのコマンドとVRTファイルが必要）
```
ogr2ogr -f "ESRI Shapefile" -s_srs EPSG:2456 -t_srs EPSG:2456 -lco GEOMETRY=AS_XY point.shp temp.vrt
```

* 標高メッシュのSHPファイルからDEM画像を作成
```
gdal_rasterize -a z -tr 2.5 2.5 -l layername point.shp dem.tif
```

* ラスタ画像の座標系変換
```
gdalwarp -s_srs EPSG:*** -t_srs EPSG:*** -of "GTiff" in.tif out.tif
```
