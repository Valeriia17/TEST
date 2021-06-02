
<!doctype html>
<html lang="en">
    <head>
        <meta charset="utf-8">
        <meta http-equiv="X-UA-Compatible" content="IE=edge">
        <meta name="viewport" content="initial-scale=1,user-scalable=no,maximum-scale=1,width=device-width">
        <meta name="mobile-web-app-capable" content="yes">
        <meta name="apple-mobile-web-app-capable" content="yes">
        <link rel="stylesheet" href="css/leaflet.css">
        <link rel="stylesheet" href="css/qgis2web.css"><link rel="stylesheet" href="css/fontawesome-all.min.css">
        <style>
        html, body, #map {
            width: 100%;
            height: 100%;
            padding: 0;
            margin: 0;
        }
        </style>
        <title></title>
    </head>
    <body>
        <div id="map">
        </div>
        <script src="js/qgis2web_expressions.js"></script>
        <script src="js/leaflet.js"></script>
        <script src="js/leaflet.rotatedMarker.js"></script>
        <script src="js/leaflet.pattern.js"></script>
        <script src="js/leaflet-hash.js"></script>
        <script src="js/Autolinker.min.js"></script>
        <script src="js/rbush.min.js"></script>
        <script src="js/labelgun.min.js"></script>
        <script src="js/labels.js"></script>
        <script src="data/Urbanextent_0.js"></script>
        <script src="data/Buildingsfootprintsinfo_1.js"></script>
        <script src="data/HeightOSMM_2.js"></script>
        <script src="data/HeightGeomni_3.js"></script>
        <script src="data/Buildingage_4.js"></script>
        <script src="data/Buildinguse_5.js"></script>
        <script>
        var map = L.map('map', {
            zoomControl:true, maxZoom:28, minZoom:1
        }).fitBounds([[54.97608116252134,-1.6173899703191592],[55.01606205203771,-1.5279479111326797]]);
        var hash = new L.Hash(map);
        map.attributionControl.setPrefix('<a href="https://github.com/tomchadwin/qgis2web" target="_blank">qgis2web</a> &middot; <a href="https://leafletjs.com" title="A JS library for interactive maps">Leaflet</a> &middot; <a href="https://qgis.org">QGIS</a>');
        var autolinker = new Autolinker({truncate: {length: 30, location: 'smart'}});
        var bounds_group = new L.featureGroup([]);
        function setBounds() {
        }
        function pop_Urbanextent_0(feature, layer) {
            var popupContent = '<table>\
                    <tr>\
                        <td colspan="2">' + (feature.properties['Fid'] !== null ? autolinker.link(feature.properties['Fid'].toLocaleString()) : '') + '</td>\
                    </tr>\
                    <tr>\
                        <td colspan="2">' + (feature.properties['FeatCode'] !== null ? autolinker.link(feature.properties['FeatCode'].toLocaleString()) : '') + '</td>\
                    </tr>\
                    <tr>\
                        <td colspan="2">' + (feature.properties['FeatDesc'] !== null ? autolinker.link(feature.properties['FeatDesc'].toLocaleString()) : '') + '</td>\
                    </tr>\
                </table>';
            layer.bindPopup(popupContent, {maxHeight: 400});
        }

        function style_Urbanextent_0_0() {
            return {
                pane: 'pane_Urbanextent_0',
                opacity: 1,
                color: 'rgba(82,82,82,1.0)',
                dashArray: '',
                lineCap: 'butt',
                lineJoin: 'miter',
                weight: 1.0, 
                fill: true,
                fillOpacity: 1,
                fillColor: 'rgba(247,247,247,1.0)',
                interactive: false,
            }
        }
        map.createPane('pane_Urbanextent_0');
        map.getPane('pane_Urbanextent_0').style.zIndex = 400;
        map.getPane('pane_Urbanextent_0').style['mix-blend-mode'] = 'normal';
        var layer_Urbanextent_0 = new L.geoJson(json_Urbanextent_0, {
            attribution: '',
            interactive: false,
            dataVar: 'json_Urbanextent_0',
            layerName: 'layer_Urbanextent_0',
            pane: 'pane_Urbanextent_0',
            onEachFeature: pop_Urbanextent_0,
            style: style_Urbanextent_0_0,
        });
        bounds_group.addLayer(layer_Urbanextent_0);
        map.addLayer(layer_Urbanextent_0);
        function pop_Buildingsfootprintsinfo_1(feature, layer) {
            var popupContent = '<table>\
                    <tr>\
                        <th scope="row">Join_Count</th>\
                        <td>' + (feature.properties['Join_Count'] !== null ? autolinker.link(feature.properties['Join_Count'].toLocaleString()) : '') + '</td>\
                    </tr>\
                    <tr>\
                        <td colspan="2">' + (feature.properties['TARGET_FID'] !== null ? autolinker.link(feature.properties['TARGET_FID'].toLocaleString()) : '') + '</td>\
                    </tr>\
                    <tr>\
                        <td colspan="2">' + (feature.properties['id'] !== null ? autolinker.link(feature.properties['id'].toLocaleString()) : '') + '</td>\
                    </tr>\
                    <tr>\
                        <td colspan="2">' + (feature.properties['unique_pro'] !== null ? autolinker.link(feature.properties['unique_pro'].toLocaleString()) : '') + '</td>\
                    </tr>\
                    <tr>\
                        <td colspan="2">' + (feature.properties['unique_bui'] !== null ? autolinker.link(feature.properties['unique_bui'].toLocaleString()) : '') + '</td>\
                    </tr>\
                    <tr>\
                        <td colspan="2">' + (feature.properties['property_a'] !== null ? autolinker.link(feature.properties['property_a'].toLocaleString()) : '') + '</td>\
                    </tr>\
                    <tr>\
                        <td colspan="2">' + (feature.properties['building_a'] !== null ? autolinker.link(feature.properties['building_a'].toLocaleString()) : '') + '</td>\
                    </tr>\
                    <tr>\
                        <td colspan="2">' + (feature.properties['mapping_bl'] !== null ? autolinker.link(feature.properties['mapping_bl'].toLocaleString()) : '') + '</td>\
                    </tr>\
                    <tr>\
                        <th scope="row">height</th>\
                        <td>' + (feature.properties['height'] !== null ? autolinker.link(feature.properties['height'].toLocaleString()) : '') + '</td>\
                    </tr>\
                    <tr>\
                        <th scope="row">age</th>\
                        <td>' + (feature.properties['age'] !== null ? autolinker.link(feature.properties['age'].toLocaleString()) : '') + '</td>\
                    </tr>\
                    <tr>\
                        <th scope="row">use</th>\
                        <td>' + (feature.properties['use'] !== null ? autolinker.link(feature.properties['use'].toLocaleString()) : '') + '</td>\
                    </tr>\
                    <tr>\
                        <th scope="row">data_level</th>\
                        <td>' + (feature.properties['data_level'] !== null ? autolinker.link(feature.properties['data_level'].toLocaleString()) : '') + '</td>\
                    </tr>\
                    <tr>\
                        <td colspan="2">' + (feature.properties['OBJECTID'] !== null ? autolinker.link(feature.properties['OBJECTID'].toLocaleString()) : '') + '</td>\
                    </tr>\
                    <tr>\
                        <td colspan="2">' + (feature.properties['os_topo_to'] !== null ? autolinker.link(feature.properties['os_topo_to'].toLocaleString()) : '') + '</td>\
                    </tr>\
                    <tr>\
                        <td colspan="2">' + (feature.properties['os_topo_ve'] !== null ? autolinker.link(feature.properties['os_topo_ve'].toLocaleString()) : '') + '</td>\
                    </tr>\
                    <tr>\
                        <th scope="row">bha_proces</th>\
                        <td>' + (feature.properties['bha_proces'] !== null ? autolinker.link(feature.properties['bha_proces'].toLocaleString()) : '') + '</td>\
                    </tr>\
                    <tr>\
                        <td colspan="2">' + (feature.properties['tileref'] !== null ? autolinker.link(feature.properties['tileref'].toLocaleString()) : '') + '</td>\
                    </tr>\
                    <tr>\
                        <th scope="row">abshmax</th>\
                        <td>' + (feature.properties['abshmax'] !== null ? autolinker.link(feature.properties['abshmax'].toLocaleString()) : '') + '</td>\
                    </tr>\
                    <tr>\
                        <th scope="row">relh2</th>\
                        <td>' + (feature.properties['relh2'] !== null ? autolinker.link(feature.properties['relh2'].toLocaleString()) : '') + '</td>\
                    </tr>\
                    <tr>\
                        <th scope="row">relhmax</th>\
                        <td>' + (feature.properties['relhmax'] !== null ? autolinker.link(feature.properties['relhmax'].toLocaleString()) : '') + '</td>\
                    </tr>\
                    <tr>\
                        <th scope="row">bha_conf</th>\
                        <td>' + (feature.properties['bha_conf'] !== null ? autolinker.link(feature.properties['bha_conf'].toLocaleString()) : '') + '</td>\
                    </tr>\
                    <tr>\
                        <th scope="row">hei_relhmx</th>\
                        <td>' + (feature.properties['hei_relhmx'] !== null ? autolinker.link(feature.properties['hei_relhmx'].toLocaleString()) : '') + '</td>\
                    </tr>\
                </table>';
            layer.bindPopup(popupContent, {maxHeight: 400});
        }

        function style_Buildingsfootprintsinfo_1_0() {
            return {
                pane: 'pane_Buildingsfootprintsinfo_1',
                opacity: 1,
                color: 'rgba(35,35,35,0.0)',
                dashArray: '',
                lineCap: 'butt',
                lineJoin: 'miter',
                weight: 1, 
                fill: true,
                fillOpacity: 1,
                fillColor: 'rgba(255,255,255,1.0)',
                interactive: true,
            }
        }
        map.createPane('pane_Buildingsfootprintsinfo_1');
        map.getPane('pane_Buildingsfootprintsinfo_1').style.zIndex = 401;
        map.getPane('pane_Buildingsfootprintsinfo_1').style['mix-blend-mode'] = 'normal';
        var layer_Buildingsfootprintsinfo_1 = new L.geoJson(json_Buildingsfootprintsinfo_1, {
            attribution: '',
            interactive: true,
            dataVar: 'json_Buildingsfootprintsinfo_1',
            layerName: 'layer_Buildingsfootprintsinfo_1',
            pane: 'pane_Buildingsfootprintsinfo_1',
            onEachFeature: pop_Buildingsfootprintsinfo_1,
            style: style_Buildingsfootprintsinfo_1_0,
        });
        bounds_group.addLayer(layer_Buildingsfootprintsinfo_1);
        map.addLayer(layer_Buildingsfootprintsinfo_1);
        function pop_HeightOSMM_2(feature, layer) {
            var popupContent = '<table>\
                    <tr>\
                        <td colspan="2">' + (feature.properties['Join_Count'] !== null ? autolinker.link(feature.properties['Join_Count'].toLocaleString()) : '') + '</td>\
                    </tr>\
                    <tr>\
                        <td colspan="2">' + (feature.properties['TARGET_FID'] !== null ? autolinker.link(feature.properties['TARGET_FID'].toLocaleString()) : '') + '</td>\
                    </tr>\
                    <tr>\
                        <td colspan="2">' + (feature.properties['id'] !== null ? autolinker.link(feature.properties['id'].toLocaleString()) : '') + '</td>\
                    </tr>\
                    <tr>\
                        <td colspan="2">' + (feature.properties['unique_pro'] !== null ? autolinker.link(feature.properties['unique_pro'].toLocaleString()) : '') + '</td>\
                    </tr>\
                    <tr>\
                        <td colspan="2">' + (feature.properties['unique_bui'] !== null ? autolinker.link(feature.properties['unique_bui'].toLocaleString()) : '') + '</td>\
                    </tr>\
                    <tr>\
                        <td colspan="2">' + (feature.properties['property_a'] !== null ? autolinker.link(feature.properties['property_a'].toLocaleString()) : '') + '</td>\
                    </tr>\
                    <tr>\
                        <td colspan="2">' + (feature.properties['building_a'] !== null ? autolinker.link(feature.properties['building_a'].toLocaleString()) : '') + '</td>\
                    </tr>\
                    <tr>\
                        <td colspan="2">' + (feature.properties['mapping_bl'] !== null ? autolinker.link(feature.properties['mapping_bl'].toLocaleString()) : '') + '</td>\
                    </tr>\
                    <tr>\
                        <td colspan="2">' + (feature.properties['height'] !== null ? autolinker.link(feature.properties['height'].toLocaleString()) : '') + '</td>\
                    </tr>\
                    <tr>\
                        <td colspan="2">' + (feature.properties['age'] !== null ? autolinker.link(feature.properties['age'].toLocaleString()) : '') + '</td>\
                    </tr>\
                    <tr>\
                        <td colspan="2">' + (feature.properties['use'] !== null ? autolinker.link(feature.properties['use'].toLocaleString()) : '') + '</td>\
                    </tr>\
                    <tr>\
                        <td colspan="2">' + (feature.properties['data_level'] !== null ? autolinker.link(feature.properties['data_level'].toLocaleString()) : '') + '</td>\
                    </tr>\
                    <tr>\
                        <td colspan="2">' + (feature.properties['OBJECTID'] !== null ? autolinker.link(feature.properties['OBJECTID'].toLocaleString()) : '') + '</td>\
                    </tr>\
                    <tr>\
                        <td colspan="2">' + (feature.properties['os_topo_to'] !== null ? autolinker.link(feature.properties['os_topo_to'].toLocaleString()) : '') + '</td>\
                    </tr>\
                    <tr>\
                        <td colspan="2">' + (feature.properties['os_topo_ve'] !== null ? autolinker.link(feature.properties['os_topo_ve'].toLocaleString()) : '') + '</td>\
                    </tr>\
                    <tr>\
                        <td colspan="2">' + (feature.properties['bha_proces'] !== null ? autolinker.link(feature.properties['bha_proces'].toLocaleString()) : '') + '</td>\
                    </tr>\
                    <tr>\
                        <td colspan="2">' + (feature.properties['tileref'] !== null ? autolinker.link(feature.properties['tileref'].toLocaleString()) : '') + '</td>\
                    </tr>\
                    <tr>\
                        <td colspan="2">' + (feature.properties['abshmax'] !== null ? autolinker.link(feature.properties['abshmax'].toLocaleString()) : '') + '</td>\
                    </tr>\
                    <tr>\
                        <td colspan="2">' + (feature.properties['relh2'] !== null ? autolinker.link(feature.properties['relh2'].toLocaleString()) : '') + '</td>\
                    </tr>\
                    <tr>\
                        <td colspan="2">' + (feature.properties['relhmax'] !== null ? autolinker.link(feature.properties['relhmax'].toLocaleString()) : '') + '</td>\
                    </tr>\
                    <tr>\
                        <td colspan="2">' + (feature.properties['bha_conf'] !== null ? autolinker.link(feature.properties['bha_conf'].toLocaleString()) : '') + '</td>\
                    </tr>\
                    <tr>\
                        <td colspan="2">' + (feature.properties['hei_relhmx'] !== null ? autolinker.link(feature.properties['hei_relhmx'].toLocaleString()) : '') + '</td>\
                    </tr>\
                </table>';
            layer.bindPopup(popupContent, {maxHeight: 400});
        }

        function style_HeightOSMM_2_0(feature) {
            if (feature.properties['relhmax'] >= 0.000000 && feature.properties['relhmax'] <= 5.000000 ) {
                return {
                pane: 'pane_HeightOSMM_2',
                opacity: 1,
                color: 'rgba(35,35,35,0.0)',
                dashArray: '',
                lineCap: 'butt',
                lineJoin: 'miter',
                weight: 1.0, 
                fill: true,
                fillOpacity: 1,
                fillColor: 'rgba(0,0,4,1.0)',
                interactive: false,
            }
            }
            if (feature.properties['relhmax'] >= 5.000000 && feature.properties['relhmax'] <= 10.000000 ) {
                return {
                pane: 'pane_HeightOSMM_2',
                opacity: 1,
                color: 'rgba(35,35,35,0.0)',
                dashArray: '',
                lineCap: 'butt',
                lineJoin: 'miter',
                weight: 1.0, 
                fill: true,
                fillOpacity: 1,
                fillColor: 'rgba(114,31,129,1.0)',
                interactive: false,
            }
            }
            if (feature.properties['relhmax'] >= 10.000000 && feature.properties['relhmax'] <= 20.000000 ) {
                return {
                pane: 'pane_HeightOSMM_2',
                opacity: 1,
                color: 'rgba(35,35,35,0.0)',
                dashArray: '',
                lineCap: 'butt',
                lineJoin: 'miter',
                weight: 1.0, 
                fill: true,
                fillOpacity: 1,
                fillColor: 'rgba(241,96,93,1.0)',
                interactive: false,
            }
            }
            if (feature.properties['relhmax'] >= 20.000000 && feature.properties['relhmax'] <= 76.800000 ) {
                return {
                pane: 'pane_HeightOSMM_2',
                opacity: 1,
                color: 'rgba(35,35,35,0.0)',
                dashArray: '',
                lineCap: 'butt',
                lineJoin: 'miter',
                weight: 1.0, 
                fill: true,
                fillOpacity: 1,
                fillColor: 'rgba(252,253,191,1.0)',
                interactive: false,
            }
            }
        }
        map.createPane('pane_HeightOSMM_2');
        map.getPane('pane_HeightOSMM_2').style.zIndex = 402;
        map.getPane('pane_HeightOSMM_2').style['mix-blend-mode'] = 'normal';
        var layer_HeightOSMM_2 = new L.geoJson(json_HeightOSMM_2, {
            attribution: '',
            interactive: false,
            dataVar: 'json_HeightOSMM_2',
            layerName: 'layer_HeightOSMM_2',
            pane: 'pane_HeightOSMM_2',
            onEachFeature: pop_HeightOSMM_2,
            style: style_HeightOSMM_2_0,
        });
        bounds_group.addLayer(layer_HeightOSMM_2);
        function pop_HeightGeomni_3(feature, layer) {
            var popupContent = '<table>\
                    <tr>\
                        <td colspan="2">' + (feature.properties['Join_Count'] !== null ? autolinker.link(feature.properties['Join_Count'].toLocaleString()) : '') + '</td>\
                    </tr>\
                    <tr>\
                        <td colspan="2">' + (feature.properties['TARGET_FID'] !== null ? autolinker.link(feature.properties['TARGET_FID'].toLocaleString()) : '') + '</td>\
                    </tr>\
                    <tr>\
                        <td colspan="2">' + (feature.properties['id'] !== null ? autolinker.link(feature.properties['id'].toLocaleString()) : '') + '</td>\
                    </tr>\
                    <tr>\
                        <td colspan="2">' + (feature.properties['unique_pro'] !== null ? autolinker.link(feature.properties['unique_pro'].toLocaleString()) : '') + '</td>\
                    </tr>\
                    <tr>\
                        <td colspan="2">' + (feature.properties['unique_bui'] !== null ? autolinker.link(feature.properties['unique_bui'].toLocaleString()) : '') + '</td>\
                    </tr>\
                    <tr>\
                        <td colspan="2">' + (feature.properties['property_a'] !== null ? autolinker.link(feature.properties['property_a'].toLocaleString()) : '') + '</td>\
                    </tr>\
                    <tr>\
                        <td colspan="2">' + (feature.properties['building_a'] !== null ? autolinker.link(feature.properties['building_a'].toLocaleString()) : '') + '</td>\
                    </tr>\
                    <tr>\
                        <td colspan="2">' + (feature.properties['mapping_bl'] !== null ? autolinker.link(feature.properties['mapping_bl'].toLocaleString()) : '') + '</td>\
                    </tr>\
                    <tr>\
                        <td colspan="2">' + (feature.properties['height'] !== null ? autolinker.link(feature.properties['height'].toLocaleString()) : '') + '</td>\
                    </tr>\
                    <tr>\
                        <td colspan="2">' + (feature.properties['age'] !== null ? autolinker.link(feature.properties['age'].toLocaleString()) : '') + '</td>\
                    </tr>\
                    <tr>\
                        <td colspan="2">' + (feature.properties['use'] !== null ? autolinker.link(feature.properties['use'].toLocaleString()) : '') + '</td>\
                    </tr>\
                    <tr>\
                        <td colspan="2">' + (feature.properties['data_level'] !== null ? autolinker.link(feature.properties['data_level'].toLocaleString()) : '') + '</td>\
                    </tr>\
                    <tr>\
                        <td colspan="2">' + (feature.properties['OBJECTID'] !== null ? autolinker.link(feature.properties['OBJECTID'].toLocaleString()) : '') + '</td>\
                    </tr>\
                    <tr>\
                        <td colspan="2">' + (feature.properties['os_topo_to'] !== null ? autolinker.link(feature.properties['os_topo_to'].toLocaleString()) : '') + '</td>\
                    </tr>\
                    <tr>\
                        <td colspan="2">' + (feature.properties['os_topo_ve'] !== null ? autolinker.link(feature.properties['os_topo_ve'].toLocaleString()) : '') + '</td>\
                    </tr>\
                    <tr>\
                        <td colspan="2">' + (feature.properties['bha_proces'] !== null ? autolinker.link(feature.properties['bha_proces'].toLocaleString()) : '') + '</td>\
                    </tr>\
                    <tr>\
                        <td colspan="2">' + (feature.properties['tileref'] !== null ? autolinker.link(feature.properties['tileref'].toLocaleString()) : '') + '</td>\
                    </tr>\
                    <tr>\
                        <td colspan="2">' + (feature.properties['abshmax'] !== null ? autolinker.link(feature.properties['abshmax'].toLocaleString()) : '') + '</td>\
                    </tr>\
                    <tr>\
                        <td colspan="2">' + (feature.properties['relh2'] !== null ? autolinker.link(feature.properties['relh2'].toLocaleString()) : '') + '</td>\
                    </tr>\
                    <tr>\
                        <td colspan="2">' + (feature.properties['relhmax'] !== null ? autolinker.link(feature.properties['relhmax'].toLocaleString()) : '') + '</td>\
                    </tr>\
                    <tr>\
                        <td colspan="2">' + (feature.properties['bha_conf'] !== null ? autolinker.link(feature.properties['bha_conf'].toLocaleString()) : '') + '</td>\
                    </tr>\
                    <tr>\
                        <td colspan="2">' + (feature.properties['hei_relhmx'] !== null ? autolinker.link(feature.properties['hei_relhmx'].toLocaleString()) : '') + '</td>\
                    </tr>\
                </table>';
            layer.bindPopup(popupContent, {maxHeight: 400});
        }

        function style_HeightGeomni_3_0(feature) {
            if (feature.properties['height'] >= 0.000000 && feature.properties['height'] <= 5.000000 ) {
                return {
                pane: 'pane_HeightGeomni_3',
                opacity: 1,
                color: 'rgba(35,35,35,0.0)',
                dashArray: '',
                lineCap: 'butt',
                lineJoin: 'miter',
                weight: 1.0, 
                fill: true,
                fillOpacity: 1,
                fillColor: 'rgba(68,1,84,1.0)',
                interactive: false,
            }
            }
            if (feature.properties['height'] >= 5.000000 && feature.properties['height'] <= 10.000000 ) {
                return {
                pane: 'pane_HeightGeomni_3',
                opacity: 1,
                color: 'rgba(35,35,35,0.0)',
                dashArray: '',
                lineCap: 'butt',
                lineJoin: 'miter',
                weight: 1.0, 
                fill: true,
                fillOpacity: 1,
                fillColor: 'rgba(49,104,142,1.0)',
                interactive: false,
            }
            }
            if (feature.properties['height'] >= 10.000000 && feature.properties['height'] <= 20.000000 ) {
                return {
                pane: 'pane_HeightGeomni_3',
                opacity: 1,
                color: 'rgba(35,35,35,0.0)',
                dashArray: '',
                lineCap: 'butt',
                lineJoin: 'miter',
                weight: 1.0, 
                fill: true,
                fillOpacity: 1,
                fillColor: 'rgba(53,183,121,1.0)',
                interactive: false,
            }
            }
            if (feature.properties['height'] >= 20.000000 && feature.properties['height'] <= 76.800000 ) {
                return {
                pane: 'pane_HeightGeomni_3',
                opacity: 1,
                color: 'rgba(35,35,35,0.0)',
                dashArray: '',
                lineCap: 'butt',
                lineJoin: 'miter',
                weight: 1.0, 
                fill: true,
                fillOpacity: 1,
                fillColor: 'rgba(253,231,37,1.0)',
                interactive: false,
            }
            }
        }
        map.createPane('pane_HeightGeomni_3');
        map.getPane('pane_HeightGeomni_3').style.zIndex = 403;
        map.getPane('pane_HeightGeomni_3').style['mix-blend-mode'] = 'normal';
        var layer_HeightGeomni_3 = new L.geoJson(json_HeightGeomni_3, {
            attribution: '',
            interactive: false,
            dataVar: 'json_HeightGeomni_3',
            layerName: 'layer_HeightGeomni_3',
            pane: 'pane_HeightGeomni_3',
            onEachFeature: pop_HeightGeomni_3,
            style: style_HeightGeomni_3_0,
        });
        bounds_group.addLayer(layer_HeightGeomni_3);
        function pop_Buildingage_4(feature, layer) {
            var popupContent = '<table>\
                    <tr>\
                        <td colspan="2">' + (feature.properties['Join_Count'] !== null ? autolinker.link(feature.properties['Join_Count'].toLocaleString()) : '') + '</td>\
                    </tr>\
                    <tr>\
                        <td colspan="2">' + (feature.properties['TARGET_FID'] !== null ? autolinker.link(feature.properties['TARGET_FID'].toLocaleString()) : '') + '</td>\
                    </tr>\
                    <tr>\
                        <td colspan="2">' + (feature.properties['id'] !== null ? autolinker.link(feature.properties['id'].toLocaleString()) : '') + '</td>\
                    </tr>\
                    <tr>\
                        <td colspan="2">' + (feature.properties['unique_pro'] !== null ? autolinker.link(feature.properties['unique_pro'].toLocaleString()) : '') + '</td>\
                    </tr>\
                    <tr>\
                        <td colspan="2">' + (feature.properties['unique_bui'] !== null ? autolinker.link(feature.properties['unique_bui'].toLocaleString()) : '') + '</td>\
                    </tr>\
                    <tr>\
                        <td colspan="2">' + (feature.properties['property_a'] !== null ? autolinker.link(feature.properties['property_a'].toLocaleString()) : '') + '</td>\
                    </tr>\
                    <tr>\
                        <td colspan="2">' + (feature.properties['building_a'] !== null ? autolinker.link(feature.properties['building_a'].toLocaleString()) : '') + '</td>\
                    </tr>\
                    <tr>\
                        <td colspan="2">' + (feature.properties['mapping_bl'] !== null ? autolinker.link(feature.properties['mapping_bl'].toLocaleString()) : '') + '</td>\
                    </tr>\
                    <tr>\
                        <td colspan="2">' + (feature.properties['height'] !== null ? autolinker.link(feature.properties['height'].toLocaleString()) : '') + '</td>\
                    </tr>\
                    <tr>\
                        <td colspan="2">' + (feature.properties['age'] !== null ? autolinker.link(feature.properties['age'].toLocaleString()) : '') + '</td>\
                    </tr>\
                    <tr>\
                        <td colspan="2">' + (feature.properties['use'] !== null ? autolinker.link(feature.properties['use'].toLocaleString()) : '') + '</td>\
                    </tr>\
                    <tr>\
                        <td colspan="2">' + (feature.properties['data_level'] !== null ? autolinker.link(feature.properties['data_level'].toLocaleString()) : '') + '</td>\
                    </tr>\
                    <tr>\
                        <td colspan="2">' + (feature.properties['OBJECTID'] !== null ? autolinker.link(feature.properties['OBJECTID'].toLocaleString()) : '') + '</td>\
                    </tr>\
                    <tr>\
                        <td colspan="2">' + (feature.properties['os_topo_to'] !== null ? autolinker.link(feature.properties['os_topo_to'].toLocaleString()) : '') + '</td>\
                    </tr>\
                    <tr>\
                        <td colspan="2">' + (feature.properties['os_topo_ve'] !== null ? autolinker.link(feature.properties['os_topo_ve'].toLocaleString()) : '') + '</td>\
                    </tr>\
                    <tr>\
                        <td colspan="2">' + (feature.properties['bha_proces'] !== null ? autolinker.link(feature.properties['bha_proces'].toLocaleString()) : '') + '</td>\
                    </tr>\
                    <tr>\
                        <td colspan="2">' + (feature.properties['tileref'] !== null ? autolinker.link(feature.properties['tileref'].toLocaleString()) : '') + '</td>\
                    </tr>\
                    <tr>\
                        <td colspan="2">' + (feature.properties['abshmax'] !== null ? autolinker.link(feature.properties['abshmax'].toLocaleString()) : '') + '</td>\
                    </tr>\
                    <tr>\
                        <td colspan="2">' + (feature.properties['relh2'] !== null ? autolinker.link(feature.properties['relh2'].toLocaleString()) : '') + '</td>\
                    </tr>\
                    <tr>\
                        <td colspan="2">' + (feature.properties['relhmax'] !== null ? autolinker.link(feature.properties['relhmax'].toLocaleString()) : '') + '</td>\
                    </tr>\
                    <tr>\
                        <td colspan="2">' + (feature.properties['bha_conf'] !== null ? autolinker.link(feature.properties['bha_conf'].toLocaleString()) : '') + '</td>\
                    </tr>\
                    <tr>\
                        <td colspan="2">' + (feature.properties['hei_relhmx'] !== null ? autolinker.link(feature.properties['hei_relhmx'].toLocaleString()) : '') + '</td>\
                    </tr>\
                </table>';
            layer.bindPopup(popupContent, {maxHeight: 400});
        }

        function style_Buildingage_4_0(feature) {
            switch(String(feature.properties['age'])) {
                case 'HISTORIC':
                    return {
                pane: 'pane_Buildingage_4',
                opacity: 1,
                color: 'rgba(35,35,35,0.0)',
                dashArray: '',
                lineCap: 'butt',
                lineJoin: 'miter',
                weight: 1.0, 
                fill: true,
                fillOpacity: 1,
                fillColor: 'rgba(0,0,4,1.0)',
                interactive: false,
            }
                    break;
                case 'INTERWAR':
                    return {
                pane: 'pane_Buildingage_4',
                opacity: 1,
                color: 'rgba(35,35,35,0.0)',
                dashArray: '',
                lineCap: 'butt',
                lineJoin: 'miter',
                weight: 1.0, 
                fill: true,
                fillOpacity: 1,
                fillColor: 'rgba(45,17,95,1.0)',
                interactive: false,
            }
                    break;
                case '[\'MIXED AGE PART HISTORIC\', \'MIXED AGE PART INTERWAR\', \'MIXED AGE PART POSTWAR\']':
                    return {
                pane: 'pane_Buildingage_4',
                opacity: 1,
                color: 'rgba(35,35,35,0.0)',
                dashArray: '',
                lineCap: 'butt',
                lineJoin: 'miter',
                weight: 1.0, 
                fill: true,
                fillOpacity: 1,
                fillColor: 'rgba(114,31,129,1.0)',
                interactive: false,
            }
                    break;
                case 'MODERN':
                    return {
                pane: 'pane_Buildingage_4',
                opacity: 1,
                color: 'rgba(35,35,35,0.0)',
                dashArray: '',
                lineCap: 'butt',
                lineJoin: 'miter',
                weight: 1.0, 
                fill: true,
                fillOpacity: 1,
                fillColor: 'rgba(182,54,121,1.0)',
                interactive: false,
            }
                    break;
                case 'POSTWAR':
                    return {
                pane: 'pane_Buildingage_4',
                opacity: 1,
                color: 'rgba(35,35,35,0.0)',
                dashArray: '',
                lineCap: 'butt',
                lineJoin: 'miter',
                weight: 1.0, 
                fill: true,
                fillOpacity: 1,
                fillColor: 'rgba(241,96,93,1.0)',
                interactive: false,
            }
                    break;
                case 'SIXTIES SEVENTIES':
                    return {
                pane: 'pane_Buildingage_4',
                opacity: 1,
                color: 'rgba(35,35,35,0.0)',
                dashArray: '',
                lineCap: 'butt',
                lineJoin: 'miter',
                weight: 1.0, 
                fill: true,
                fillOpacity: 1,
                fillColor: 'rgba(254,175,119,1.0)',
                interactive: false,
            }
                    break;
                case 'UNCLASSIFIED':
                    return {
                pane: 'pane_Buildingage_4',
                opacity: 1,
                color: 'rgba(35,35,35,0.0)',
                dashArray: '',
                lineCap: 'butt',
                lineJoin: 'miter',
                weight: 1.0, 
                fill: true,
                fillOpacity: 1,
                fillColor: 'rgba(252,253,191,1.0)',
                interactive: false,
            }
                    break;
            }
        }
        map.createPane('pane_Buildingage_4');
        map.getPane('pane_Buildingage_4').style.zIndex = 404;
        map.getPane('pane_Buildingage_4').style['mix-blend-mode'] = 'normal';
        var layer_Buildingage_4 = new L.geoJson(json_Buildingage_4, {
            attribution: '',
            interactive: false,
            dataVar: 'json_Buildingage_4',
            layerName: 'layer_Buildingage_4',
            pane: 'pane_Buildingage_4',
            onEachFeature: pop_Buildingage_4,
            style: style_Buildingage_4_0,
        });
        bounds_group.addLayer(layer_Buildingage_4);
        function pop_Buildinguse_5(feature, layer) {
            var popupContent = '<table>\
                    <tr>\
                        <td colspan="2">' + (feature.properties['Join_Count'] !== null ? autolinker.link(feature.properties['Join_Count'].toLocaleString()) : '') + '</td>\
                    </tr>\
                    <tr>\
                        <td colspan="2">' + (feature.properties['TARGET_FID'] !== null ? autolinker.link(feature.properties['TARGET_FID'].toLocaleString()) : '') + '</td>\
                    </tr>\
                    <tr>\
                        <td colspan="2"><strong>id</strong><br />' + (feature.properties['id'] !== null ? autolinker.link(feature.properties['id'].toLocaleString()) : '') + '</td>\
                    </tr>\
                    <tr>\
                        <td colspan="2">' + (feature.properties['unique_pro'] !== null ? autolinker.link(feature.properties['unique_pro'].toLocaleString()) : '') + '</td>\
                    </tr>\
                    <tr>\
                        <td colspan="2">' + (feature.properties['unique_bui'] !== null ? autolinker.link(feature.properties['unique_bui'].toLocaleString()) : '') + '</td>\
                    </tr>\
                    <tr>\
                        <td colspan="2">' + (feature.properties['property_a'] !== null ? autolinker.link(feature.properties['property_a'].toLocaleString()) : '') + '</td>\
                    </tr>\
                    <tr>\
                        <td colspan="2">' + (feature.properties['building_a'] !== null ? autolinker.link(feature.properties['building_a'].toLocaleString()) : '') + '</td>\
                    </tr>\
                    <tr>\
                        <td colspan="2">' + (feature.properties['mapping_bl'] !== null ? autolinker.link(feature.properties['mapping_bl'].toLocaleString()) : '') + '</td>\
                    </tr>\
                    <tr>\
                        <td colspan="2">' + (feature.properties['height'] !== null ? autolinker.link(feature.properties['height'].toLocaleString()) : '') + '</td>\
                    </tr>\
                    <tr>\
                        <td colspan="2">' + (feature.properties['age'] !== null ? autolinker.link(feature.properties['age'].toLocaleString()) : '') + '</td>\
                    </tr>\
                    <tr>\
                        <td colspan="2">' + (feature.properties['use'] !== null ? autolinker.link(feature.properties['use'].toLocaleString()) : '') + '</td>\
                    </tr>\
                    <tr>\
                        <td colspan="2">' + (feature.properties['data_level'] !== null ? autolinker.link(feature.properties['data_level'].toLocaleString()) : '') + '</td>\
                    </tr>\
                    <tr>\
                        <td colspan="2">' + (feature.properties['OBJECTID'] !== null ? autolinker.link(feature.properties['OBJECTID'].toLocaleString()) : '') + '</td>\
                    </tr>\
                    <tr>\
                        <td colspan="2">' + (feature.properties['os_topo_to'] !== null ? autolinker.link(feature.properties['os_topo_to'].toLocaleString()) : '') + '</td>\
                    </tr>\
                    <tr>\
                        <td colspan="2">' + (feature.properties['os_topo_ve'] !== null ? autolinker.link(feature.properties['os_topo_ve'].toLocaleString()) : '') + '</td>\
                    </tr>\
                    <tr>\
                        <td colspan="2">' + (feature.properties['bha_proces'] !== null ? autolinker.link(feature.properties['bha_proces'].toLocaleString()) : '') + '</td>\
                    </tr>\
                    <tr>\
                        <td colspan="2">' + (feature.properties['tileref'] !== null ? autolinker.link(feature.properties['tileref'].toLocaleString()) : '') + '</td>\
                    </tr>\
                    <tr>\
                        <td colspan="2">' + (feature.properties['abshmax'] !== null ? autolinker.link(feature.properties['abshmax'].toLocaleString()) : '') + '</td>\
                    </tr>\
                    <tr>\
                        <td colspan="2">' + (feature.properties['relh2'] !== null ? autolinker.link(feature.properties['relh2'].toLocaleString()) : '') + '</td>\
                    </tr>\
                    <tr>\
                        <td colspan="2">' + (feature.properties['relhmax'] !== null ? autolinker.link(feature.properties['relhmax'].toLocaleString()) : '') + '</td>\
                    </tr>\
                    <tr>\
                        <td colspan="2">' + (feature.properties['bha_conf'] !== null ? autolinker.link(feature.properties['bha_conf'].toLocaleString()) : '') + '</td>\
                    </tr>\
                    <tr>\
                        <td colspan="2">' + (feature.properties['hei_relhmx'] !== null ? autolinker.link(feature.properties['hei_relhmx'].toLocaleString()) : '') + '</td>\
                    </tr>\
                </table>';
            layer.bindPopup(popupContent, {maxHeight: 400});
        }

        function style_Buildinguse_5_0(feature) {
            switch(String(feature.properties['use'])) {
                case '[\'COMMUNITY - EDUCATIONAL\', \'COMMUNITY - GOVERNMENTAL (CENTRAL AND LOCAL)\', \'COMMUNITY - HEALTH\', \'COMMUNITY - INSTITUTIONAL AND COMMUNAL ACCOMMODATION\', \'COMMUNITY - RELIGIOUS\']':
                    return {
                pane: 'pane_Buildinguse_5',
                opacity: 1,
                color: 'rgba(35,35,35,0.0)',
                dashArray: '',
                lineCap: 'butt',
                lineJoin: 'miter',
                weight: 1.0, 
                fill: true,
                fillOpacity: 1,
                fillColor: 'rgba(0,0,4,1.0)',
                interactive: false,
            }
                    break;
                case 'INDUSTRY - MANUFACTURING/PROCESSING':
                    return {
                pane: 'pane_Buildinguse_5',
                opacity: 1,
                color: 'rgba(35,35,35,0.0)',
                dashArray: '',
                lineCap: 'butt',
                lineJoin: 'miter',
                weight: 1.0, 
                fill: true,
                fillOpacity: 1,
                fillColor: 'rgba(59,15,111,1.0)',
                interactive: false,
            }
                    break;
                case 'OFFICE ONLY':
                    return {
                pane: 'pane_Buildinguse_5',
                opacity: 1,
                color: 'rgba(35,35,35,0.0)',
                dashArray: '',
                lineCap: 'butt',
                lineJoin: 'miter',
                weight: 1.0, 
                fill: true,
                fillOpacity: 1,
                fillColor: 'rgba(140,41,129,1.0)',
                interactive: false,
            }
                    break;
                case 'RECREATION AND LEISURE':
                    return {
                pane: 'pane_Buildinguse_5',
                opacity: 1,
                color: 'rgba(35,35,35,0.0)',
                dashArray: '',
                lineCap: 'butt',
                lineJoin: 'miter',
                weight: 1.0, 
                fill: true,
                fillOpacity: 1,
                fillColor: 'rgba(222,73,105,1.0)',
                interactive: false,
            }
                    break;
                case 'RESIDENTIAL ONLY':
                    return {
                pane: 'pane_Buildinguse_5',
                opacity: 1,
                color: 'rgba(35,35,35,0.0)',
                dashArray: '',
                lineCap: 'butt',
                lineJoin: 'miter',
                weight: 1.0, 
                fill: true,
                fillOpacity: 1,
                fillColor: 'rgba(254,159,109,1.0)',
                interactive: false,
            }
                    break;
                case '[\'RETAIL ONLY\', \'RETAIL WITH OFFICE/RESIDENTIAL ABOVE\', \'GENERAL COMMERCIAL - MIXED USE\']':
                    return {
                pane: 'pane_Buildinguse_5',
                opacity: 1,
                color: 'rgba(35,35,35,0.0)',
                dashArray: '',
                lineCap: 'butt',
                lineJoin: 'miter',
                weight: 1.0, 
                fill: true,
                fillOpacity: 1,
                fillColor: 'rgba(252,253,191,1.0)',
                interactive: false,
            }
                    break;
            }
        }
        map.createPane('pane_Buildinguse_5');
        map.getPane('pane_Buildinguse_5').style.zIndex = 405;
        map.getPane('pane_Buildinguse_5').style['mix-blend-mode'] = 'normal';
        var layer_Buildinguse_5 = new L.geoJson(json_Buildinguse_5, {
            attribution: '',
            interactive: false,
            dataVar: 'json_Buildinguse_5',
            layerName: 'layer_Buildinguse_5',
            pane: 'pane_Buildinguse_5',
            onEachFeature: pop_Buildinguse_5,
            style: style_Buildinguse_5_0,
        });
        bounds_group.addLayer(layer_Buildinguse_5);
        var baseMaps = {};
    
        </script>
    </body>
</html>
