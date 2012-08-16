    // JavaScript Document  
    var map = "";  
    var _isBMap_ = typeof BMap !== "undefined";  
    var PlayBack = function(mapId,user_id,productType,sudu, url){  
        this.container = mapId;  
        this.user_id = user_id;  
        this.map = null;  
        this.productType = productType;  
        this.overSpeed = sudu<60?80:sudu;  
        this.AJAX_URL = url || "";  
        this.REQUESR_URL = "http://his.10086care.com/GetDataService?method=getHistoryMByMUtc";
        this.MAP_CENTER_LAT = 22.573978188551297;  
        this.MAP_CENTER_LNG = 113.92078757286072;  
        this.DEFAULT_DAYS = 6*24*60*60;  
        this.RECORDS_LENGTH = 1000;  
        this.MARKERS_OBJ = {};  
        this.STATIC_MARKER = [];  
        this.mapType =(typeof BMap == 'undefined')?"GOOGLE":"BAIDU";  
        this.DEFAULT_ZOOM = 5;  
        this.DISTANCE = 0;  
        this.POLY_LINE_MARKER = [];  
        this.DATA_REQUEST = true;  
        this.FROM_TIME = null;  
        this.TO_TIME = null;  
        this.NEXT_TIME = null;  
        this.LAST_DATA = [];  
        this.PRE_DATE_TIMR = null;  
        this.LAST_DATA_ = [];  
        this.PRE_DATE_TIMR_ = null;  
        this.RUN_TIME = 0;  
        this.STOP_TIME = 0;  
        this.EXCURSION_COUNT = 0;  
        this.FRIST_LOAD = true;  
        this.TIMER = "-1";  
        this.HISTORY_PLAY_FLAG = true;  
        this.Frequency = null;  
        this.BUTTONS_ID = ["PLAY","STOP"];  
        this.PLAY_OVER = false ;  
        this.CROSS_DATA_1 = null;  
        this.CROSS_DATA_2 = null;  
        this.GL = false;  
        this.needGetData = false;   
    };  
    PlayBack.prototype.createMap = function(lang){  
        this.lang = lang;  
        this.map = new goome.maps.Map({id:"map",lang:lang,lat:this.MAP_CENTER_LAT,lng:this.MAP_CENTER_LNG,zoom:this.DEFAULT_ZOOM});  
        goome.maps.event.addListener(this.map,"mousemove",PlayBack.mapMouseMove);  
    };  
    PlayBack.prototype.getDataFrist = function(from,to,q){
        this.buttonAttribute(this.BUTTONS_ID[0],true,true);  
        if(from==""||to=="") return;  
        var FROM_TIME = new Date(from.replace(/-/g, "/"));  
        var TO_TIME = new Date(to.replace(/-/g, "/"));  
        PlayBack.RUN_TIME = 0;   
          
        var timeDiff = (TO_TIME - FROM_TIME) / 1000;  
        if(timeDiff < 0){  
            alert(lg.distime);  
            this.buttonAttribute(this.BUTTONS_ID[0],false,true);  
            return;  
        }  
        if(this.FRIST_LOAD){  
            this.FROM_TIME = from;  
            this.TO_TIME = to;  
            this.NEXT_TIME = from;  
        }else{  
            PlayBack.HISTORY_PLAY_FLAG = true;  
            if(getTimeDiff(to,this.TO_TIME)>10||!PlayBack.PLAY_OVER){
                PlayBack.DATA_REQUEST = true;  
            }else{  
                PlayBack.DATA_REQUEST = false;  
            }  
            if(this.FROM_TIME!=from){  
                clearTimeout(this.TIMER);  
                this.GL = false;  
                this.clearOverLayer();  
                this.POLY_LINE_MARKER = [];  
                this.FRIST_LOAD = true;  
                this.DISTANCE = 0;  
                this.FROM_TIME = from;  
                this.NEXT_TIME = from;  
                this.TO_TIME = to;  
            }else{  
                if(getTimeDiff(to,this.TO_TIME)<=10&&PlayBack.PLAY_OVER){  
                    alert(lg.playOverTip[0] + PlayBack.FROM_TIME +lg.playOverTip[1] + PlayBack.TO_TIME);  
                    this.buttonAttribute(this.BUTTONS_ID[0],false,true);  
                    return;  
                }  
            }  
        }  
        this.Frequency = q||100;  
        if(!this.FRIST_LOAD&&!PlayBack.PLAY_OVER){
            this.TO_TIME = to;  
            PlayBack.buttonAttribute(PlayBack.BUTTONS_ID[0],false,false);  
        }else{        
            this.TO_TIME = to;  
            this.PLAY_OVER = false;  
            this.ajaxRequest();  
        }  
    };  
    PlayBack.prototype.getDataCallBack = function(msg){ 
        document.getElementById('tip').style.display = "none";  
        PlayBack.buttonAttribute(PlayBack.BUTTONS_ID[0],false,true);  
        if(!msg){  
            alert(lg.playOverTip[0] + PlayBack.FROM_TIME +lg.playOverTip[1] + PlayBack.TO_TIME);  
            var text = PlayBack.getTxtByCount();  
            if(PlayBack.MARKERS_OBJ.update) PlayBack.MARKERS_OBJ.update({text:text});  
            PlayBack.buttonAttribute(PlayBack.BUTTONS_ID[0],false,true);  
            PlayBack.PLAY_OVER = true ;  
            return;  
        }  
        PlayBack.buttonAttribute(PlayBack.BUTTONS_ID[0],true,false);  
        if(msg){  
            PlayBack.GL = false;  
            var poly = [];  
            var pArray = []; 
            if(!PlayBack.FRIST_LOAD&&PlayBack.LAST_DATA.length>0){
                poly = [new goome.maps.LatLng(PlayBack.LAST_DATA[1], PlayBack.LAST_DATA[0])];  
            }  
            var tem = msg.split(";");  
            if(PlayBack.FRIST_LOAD){  
                PlayBack.LAST_DATA_ = tem[0].split(",");  
                PlayBack.PRE_DATE_TIMR_ = PlayBack.LAST_DATA_[2];  
            }   
            var dateLen = tem.length-1;  
            for(var i=0;i<dateLen;i++){  
                var flag = true;  
                var rs = tem[i].split(",");           
                var _diffTime = getTimeDiff(utcToLocal(rs[2]),utcToLocal(PlayBack.LAST_DATA_[2]));  
                var _dis_time = getTimeDiff(utcToLocal(rs[2]),utcToLocal(PlayBack.PRE_DATE_TIMR_));
                PlayBack.LAST_DATA_ = rs;  
                PlayBack.PRE_DATE_TIMR_ = rs[2];  
                if((PlayBack.productType.indexOf("GT02")>-1||PlayBack.productType=="LY-H810")){
                    
                    if(_dis_time > (PlayBack.lang == "en" ? 300 : 30 )){  
                        PlayBack.EXCURSION_COUNT ++;  
                        rs = [PlayBack.LAST_DATA_[0],PlayBack.LAST_DATA_[1],rs[2],0];  
                        if(i==(dateLen-1))PlayBack.GL = true;  
                        continue;  
                    }  
                    if(rs[3] < 5){  
                        PlayBack.EXCURSION_COUNT ++;  
                        rs = [PlayBack.LAST_DATA_[0],PlayBack.LAST_DATA_[1],rs[2],0];  
                        if(i==(dateLen-1))PlayBack.GL = true;  
                        continue;  
                    }  
                    if(rs[3] < 10 && PlayBack.EXCURSION_COUNT > 5&&rs[3] >= 5 ){  
                        PlayBack.EXCURSION_COUNT ++;  
                        rs = [PlayBack.LAST_DATA_[0],PlayBack.LAST_DATA_[1],rs[2],0];  
                        if(i==(dateLen-1))PlayBack.GL = true;  
                        continue;  
                    }  
                    if(rs[3] >= 10 && rs[3] < 15 && PlayBack.EXCURSION_COUNT > 8 && PlayBack.LAST_DATA_[3] < 5){  
                        PlayBack.EXCURSION_COUNT ++;  
                        rs = [PlayBack.LAST_DATA_[0],PlayBack.LAST_DATA_[1],rs[2],0];  
                        if(i==(dateLen-1))PlayBack.GL = true; 
                        continue;  
                    }  
                    PlayBack.EXCURSION_COUNT = 0;  
                    poly.push(new goome.maps.LatLng(rs[1], rs[0]));  
                    pArray.push(rs);  
                }else{  
                    poly.push(new goome.maps.LatLng(rs[1], rs[0]));  
                    pArray.push(rs);  
                }  
            }  
            if((tem.length-1) == PlayBack.RECORDS_LENGTH){  
                PlayBack.NEXT_TIME = tem[tem.length-2].split(",")[2].split(".")[0];  
                PlayBack.DATA_REQUEST = true;  
                PlayBack.needGetData = true;  
            }else{  
                PlayBack.needGetData = false;   
                PlayBack.DATA_REQUEST = false;  
                  
                if(PlayBack.GL){  
                    poly.push(new goome.maps.LatLng(PlayBack.LAST_DATA_[1], PlayBack.LAST_DATA_[0]));  
                    pArray.push(PlayBack.LAST_DATA_);  
                }  
            }  
            var flightPath = new goome.maps.Polyline({path:poly,strokeColor:"#00FF00",strokeOpacity:0.9,strokeWeight:5});   
            flightPath.setMap(PlayBack.map);  
            PlayBack.POLY_LINE_MARKER.push(flightPath);  
            PlayBack.playMarker(pArray);  
        }  
    };  
      
    PlayBack.prototype.playMarker = function(array){
        if(PlayBack.FRIST_LOAD){  
            var txt = "";  
            if(array.length==0){  
                PlayBack.FRIST_LOAD = false;  
                PlayBack.LAST_DATA = PlayBack.LAST_DATA_;  
                PlayBack.PRE_DATE_TIMR = PlayBack.PRE_DATE_TIMR_;  
                txt = PlayBack.getTxtByRecord(PlayBack.LAST_DATA);  
                PlayBack.ajaxRequest();  
            }else{  
                PlayBack.LAST_DATA = array[0];  
                PlayBack.PRE_DATE_TIMR = array[0][2];  
                txt = PlayBack.getTxtByRecord(array[0]);  
            }  
            var point = new goome.maps.LatLng(PlayBack.LAST_DATA[1],PlayBack.LAST_DATA[0]);  
            PlayBack.map.setCenter(point);  
            PlayBack.map.setZoom(13);  
            PlayBack.MARKERS_OBJ = new PopupMarker({position:point,map:PlayBack.map,icon:"green.gif",text:txt,showpop:true});  
            PlayBack.POLY_LINE_MARKER.push(PlayBack.MARKERS_OBJ);  
            if(array.length==0)return;  
        }  
        var i = 0;        
        var paly = function() {  
            if(PlayBack.HISTORY_PLAY_FLAG) {  
                if(i<array.length) {   
                    if(array[i][3]>PlayBack.overSpeed){  
                        var color = "#FF00FF";  
                        if(array[i][3]>1.5*PlayBack.overSpeed)color = "#FF0000";  
                        var points = [new goome.maps.LatLng(array[i][1], array[i][0]),new goome.maps.LatLng(PlayBack.LAST_DATA[1], PlayBack.LAST_DATA[0])];  
                        var FP = new goome.maps.Polyline({path:points,strokeColor:color,strokeOpacity:0.9,strokeWeight:5});      
                        FP.setMap(PlayBack.map);  
                        PlayBack.POLY_LINE_MARKER.push(FP);  
                    }  
                    PlayBack.play(array[i]);  
                    i++;              
                    PlayBack.TIMER = setTimeout(paly,PlayBack.Frequency);  
                }else{  
                    if(PlayBack.DATA_REQUEST && PlayBack.needGetData){  
                        PlayBack.ajaxRequest();  
                    }else{  
                        alert(lg.playOverTip[0] + PlayBack.FROM_TIME +lg.playOverTip[1] + PlayBack.TO_TIME);  
                        var text = PlayBack.getTxtByCount();  
                        PlayBack.MARKERS_OBJ.update({text:text});  
                        PlayBack.buttonAttribute(PlayBack.BUTTONS_ID[0],false,true);  
                        PlayBack.PLAY_OVER = true ;  
                        PlayBack.NEXT_TIME = PlayBack.TO_TIME.split(".")[0];  
                    }  
                }  
            } else {  
                PlayBack.TIMER = setTimeout(paly,PlayBack.Frequency);  
            }  
        };  
        if(PlayBack.FRIST_LOAD){  
            PlayBack.FRIST_LOAD = false;  
            setTimeout(paly,1000);  
        }else{  
            paly();  
        }  
    };  
    PlayBack.prototype.ajaxRequest = function(){  
        var mdTime = document.getElementById('mdTime').value;  
        PlayBack.NEXT_TIME = (PlayBack.NEXT_TIME < mdTime ? mdTime : PlayBack.NEXT_TIME);  
        var parms = "&userID="+PlayBack.user_id+"&mapType="+PlayBack.mapType+"&pwd=123456&from="+localToUtc(PlayBack.NEXT_TIME)+"&to="+localToUtc(PlayBack.TO_TIME)+"&t="+new Date().getTime();  
        var loadDiv = document.getElementById('tip');  
        loadDiv.style.display = "block";  
        loadDiv.style.top = (document.documentElement.clientHeight -20)/2+"px";  
        loadDiv.style.left = (document.documentElement.clientWidth -150)/2+"px";  
        _.ajax.jsonp( PlayBack.AJAX_URL + PlayBack.REQUESR_URL + parms+"&callback=PlayBack.getDataCallBack");  
    };  
    PlayBack.prototype.getTxtByRecord = function(record){
        var html=[];  
        html.push('<font>');  
        html.push('<span style="font-weight:bold;">'+lg.speed+':</span>'+record[3]+lg.kPerH+'<br/>');  
        html.push('<span style="font-weight:bold;">'+lg.movement+':</span>'+formatKm2M(PlayBack.DISTANCE)+'<br/>');  
        html.push('<span style="font-weight:bold;">'+lg.sign+':</span>'+utcToLocal(record[2])+'<br/>');  
        if(PlayBack.STOP_TIME>0){  
            html.push('<span style="font-weight:bold;">'+lg.idle+':</span>'+exchangeTime(PlayBack.STOP_TIME)+'<br/>');  
        }  
        html.push('</font>');  
        return html.join("");  
    };  
    PlayBack.prototype.getTxtByCount = function(){ 
        var total = getTimeDiff(PlayBack.TO_TIME,PlayBack.FROM_TIME);  
        var html=[];  
        html.push('<font>');  
        html.push('<span style="font-weight:bold;">'+lg.totalTime+':</span>'+exchangeTime(total)+'<br/>');  
        html.push('<span style="font-weight:bold;">'+lg.movement+':</span>'+formatKm2M(PlayBack.DISTANCE)+'<br/>');  
        html.push('<span style="font-weight:bold;">'+lg.duration+':</span>'+(exchangeTime(PlayBack.RUN_TIME)||0)+'<br/>');  
        html.push('<span style="font-weight:bold;">'+lg.idle+':</span>'+exchangeTime(total-PlayBack.RUN_TIME)+'<br/>');  
        html.push('</font>');  
        return html.join("");  
    };  
    PlayBack.prototype.filterExcursion = function(array){
        PlayBack.EXCURSION_COUNT ++;  
        array[3] = 0;  
        var text = PlayBack.getTxtByRecord(array);  
        PlayBack.MARKERS_OBJ.update({text:text});  
    };  
    PlayBack.prototype.play = function(array){  
        array[2] = utcToLocal(array[2]);  
        var _diffTime = getTimeDiff(array[2],utcToLocal(PlayBack.LAST_DATA[2]));
        var _dis_time = getTimeDiff(array[2],utcToLocal(PlayBack.PRE_DATE_TIMR));
        PlayBack.PRE_DATE_TIMR = array[2];  
        if(_diffTime>600){  
            PlayBack.createStaticMarker(array[2],_diffTime);  
        }  
        var latlng = new goome.maps.LatLng(array[1],array[0]);  
        PlayBack.DISTANCE = distance(PlayBack.LAST_DATA[1],PlayBack.LAST_DATA[0],array[1],array[0],PlayBack.DISTANCE);  
        var text = PlayBack.getTxtByRecord(array);  
        PlayBack.MARKERS_OBJ.update({position:latlng,text:text});  
        var bound = PlayBack.map.getBounds();  
        if(!bound.contains(latlng)){
            if(_isBMap_){  
                PlayBack.map.setCenter(latlng);  
            }else{  
                PlayBack.map.panTo(latlng);  
            }  
        }  
        if(array[3]>0){  
            if(_diffTime>180){ 
                PlayBack.STOP_TIME +=_diffTime;  
            }else{
                PlayBack.RUN_TIME +=_diffTime;  
            }  
            PlayBack.LAST_DATA = array;  
        }  
    };  
    PlayBack.prototype.createStaticMarker = function(stime,dis_time){  
        var txt = lg.idle+"："+exchangeTime(dis_time)+"<br>"+lg.start+PlayBack.LAST_DATA[2]+"<br>"+lg.end+stime;  
        var point = new goome.maps.LatLng(PlayBack.LAST_DATA[1],PlayBack.LAST_DATA[0]);  
        var marker = new PopupMarker({position:point,map:PlayBack.map,icon:"gray.gif",text:txt,showpop:false});  
        PlayBack.STATIC_MARKER.push(marker);  
    };  
    PlayBack.prototype.stopPlay = function(){  
        PlayBack.buttonAttribute(PlayBack.BUTTONS_ID[1],true,false);  
        PlayBack.HISTORY_PLAY_FLAG = false;  
    };  
    PlayBack.prototype.clearOverLayer = function(){
        for(var i=0;i<PlayBack.POLY_LINE_MARKER.length;i++){  
            PlayBack.POLY_LINE_MARKER[i].setMap(null);  
        }  
        for(var j=0;j<PlayBack.STATIC_MARKER.length;j++){  
            PlayBack.STATIC_MARKER[j].setMap(null);  
        }  
    };  
    PlayBack.prototype.buttonAttribute = function(id,bool,show){  
        for(var i=0;i<this.BUTTONS_ID.length;i++){  
            if(this.BUTTONS_ID[i]==id){  
                document.getElementById(this.BUTTONS_ID[i]).disabled = bool;  
                if(show)  
                    document.getElementById(this.BUTTONS_ID[i]).style.display = "";  
                else   
                    document.getElementById(this.BUTTONS_ID[i]).style.display = "none";  
            }else{  
                if(!show) document.getElementById(this.BUTTONS_ID[i]).style.display = "";  
                else document.getElementById(this.BUTTONS_ID[i]).style.display = "none";  
                document.getElementById(this.BUTTONS_ID[i]).disabled = false;  
            }  
        }  
    };  
    PlayBack.prototype.mapMouseMove=function(event){  
        var latlng=event.latLng;  
        var markpoint=this.fromLatLngToDivPixel(latlng);  
        for(var i=0;i<PlayBack.STATIC_MARKER.length;i++){  
            var point=this.fromLatLngToDivPixel(PlayBack.STATIC_MARKER[i].latlng());  
            if(point.x<(markpoint.x+7)&&point.x>(markpoint.x-7)&&point.y<(markpoint.y+15)&&point.y>(markpoint.y-5)){  
                PlayBack.STATIC_MARKER[i].show();  
                return;  
            }else{  
                PlayBack.STATIC_MARKER[i].hide();  
            }  
        }  
    };  