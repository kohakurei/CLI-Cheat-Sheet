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

* gdal2tilesの仕組み
1. 引数に従ってプロセスの設定値を取り込む
2. メタデータ～～
3. 基準となるズームレベルのタイルを作成
4. それ以外のズームレベルのタイルを作成
