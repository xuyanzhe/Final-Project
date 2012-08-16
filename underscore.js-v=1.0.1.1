
function _(id){
 return document.getElementById(id);
}
_._ = function (searchClass, node) {
 var result = [], sc = searchClass.split('.'), tag;
 if(sc.length ===2){
  searchClass = sc[1];
  tag = sc[0]||'*';
 }else{
  return null;
 }
 if(document.getElementsByClassName){
  var nodes =  (node || document).getElementsByClassName(searchClass);
  for(var i=0 ;node = nodes[i++];){
   if(tag !== "*" && node.tagName === tag.toUpperCase()){
    result.push(node);
   }else{
    result.push(node);
   }
  }
    }else{
        if ( node == null )
                node = document;
        var els = node.getElementsByTagName(tag);
        var elsLen = els.length;
        var pattern = new RegExp("(^|\\s)"+searchClass+"(\\s|$)");
        for (i = 0, j = 0; i < elsLen; i++) {
   if ( pattern.test(els[i].className) ) {
    result[j] = els[i];
    j++;
   }
        }
    }
 return result;
};

_.isIE = (function(){
    var undef, v = 3,
        div = document.createElement('div'),
        all = div.getElementsByTagName('i');
    while (
        div.innerHTML = '<!--[if gt IE ' + (++v) + ']><i></i><![endif]-->',
        all[0]
    );
    return v > 4 ? v : undef;
}());

_.isArray = function(o){
 return Object.prototype.toString.call(o) === '[object Array]';
};
_.css = function (el,cssText,overWrite){
 if(el&&el.style){
  if(overWrite)
   el.style.cssText = cssText;
  else
   el.style.cssText += ';'+ cssText;
 }
};

_.css.append = function(cssText,id){
 var css = document.createElement('style') ,head = document.head || document.getElementsByTagName("head")[0];
 if(id){
  css.setAttribute('id',id);
 }
    css.setAttribute('type', 'text/css');

    if(css.styleSheet) {
        css.styleSheet.cssText = cssText;
    } else {
        css.appendChild(document.createTextNode(cssText));
    }
    head.appendChild(css);
};

_.css.toggle = function(node,cls,context){
 context = context || document.body;
 var clsArr = cls.split('.');
 if(clsArr.length !=2)return;
 var tag = clsArr[0], className = clsArr[1];
 var olds = _._(cls,context), len = olds.length, i = 0;
 for(;i<len;i++){
  olds[i].className = olds[i].className.replace(className,'');
 }
 var current = node.className;
 if(current.indexOf(className)== -1){
  node.className = current+ ' ' + className;
 }
};
_.dom = function(){};

_.dom.append = function(parent,tagName){
 var node = document.createElement(tagName);
 parent.appendChild(node);
 return node;
};

_.dom.remove = function(n){
 var d;
 if(_.isIE){
        if(n && n.tagName != 'BODY'){
            d = d || document.createElement('div');
            d.appendChild(n);
            d.innerHTML = '';
        }
 }else{
     if(n && n.parentNode && n.tagName != 'BODY'){
         n.parentNode.removeChild(n);
     }
 }
};

_.dom.purdge = function(d){
    var a = d.attributes, i, l, n;
    if (a) {
        l = a.length;
        for (i = 0; i < l; i += 1) {
            n = a[i].name;
            if (typeof d[n] === 'function') {
                d[n] = null;
            }
        }
    }
    a = d.childNodes;
    if (a) {
        l = a.length;
        for (i = 0; i < l; i += 1) {
            _.dom.purdge(d.childNodes[i]);
        }
    }
};
_.ajax = function(){};

(function(){
    _.ajax.TIMEOUT_REQUEST = [];
 if(_.isIE){
  _.ajax.SCRIPT_ID = 'ie_script_for_jsonp';
  _.ajax.SCRIPT_USED = false;
  _.ajax.WAIT_TIME = 100;
  _.ajax.TIMEOUT = 1500;

  _.ajax.LAST_USED_TIME = 0;
  var script = document.createElement('script'), head = document.head || document.getElementsByTagName('head')[0];
  script.setAttribute('id',_.ajax.SCRIPT_ID);
  script.onreadystatechange = function(){
   if (this.readyState == "loaded" || this.readyState == "complete"){
    _.ajax.SCRIPT_USED = false;
   }
  };
  head.appendChild(script);
 }
})();

_.ajax.jsonp = function(url){
 var script, now = new Date().getTime(),
  requestUrl = url + (url.indexOf('?')>-1?'&timestamp=':'?timestamp=') + now,
  head = document.head || document.getElementsByTagName('head')[0];
 if(_.isIE){
  script = document.getElementById(_.ajax.SCRIPT_ID);
  if(_.ajax.SCRIPT_USED){
   if(_.ajax.LAST_USED_TIME === 0)
    _.ajax.LAST_USED_TIME = now;
   if((now - _.ajax.LAST_USED_TIME) > _.ajax.TIMEOUT){
    _.ajax.LAST_USED_TIME = now;
    if(_.ajax.TIMEOUT_REQUEST.length>=1000)
     _.ajax.TIMEOUT_REQUEST.length = 0;
    _.ajax.TIMEOUT_REQUEST.push(script.src.split('&timestamp=')[0]);
    script.src = requestUrl;
   }else{
    setTimeout(function(){_.ajax.jsonp(url);},_.ajax.WAIT_TIME);
   }
  }else{
   _.ajax.SCRIPT_USED = true;
   _.ajax.LAST_USED_TIME = now;
   script.src = requestUrl;
  }
 }else{
  script = document.createElement('script');
  head.appendChild(script);
  script.onload = function(){
   this.onload = null;
   this.parentNode.removeChild(this);
  };
        script.onerror = function(){
            _.ajax.TIMEOUT_REQUEST.push(this.src);
        };
  script.src = requestUrl;
 }
};

_.ajax.getScript = function(url,callback){
 var script, head = document.head || document.getElementsByTagName('head')[0], now = new Date().getTime();
 script = _.dom.append(head,'script');
 if(callback){
  if(url.indexOf("?")>-1){
   url = "&callback=" + callback ;
  }else{
   url = "?callback=" + callback ;
  }
 }

 if(url.indexOf('callback=')>0){
  url += "&timestamp=" + now;
 }
 script.src = url;
};

_.ajax.getScripts = function(urlArray){
 if(_.isArray(urlArray)){
  for(var index in urlArray){
   _.ajax.getScript(urlArray[index]);
  }
 }
};

_.extend =  function(child,parent) {
 var F = function() {};
 F.prototype = parent.prototype;
 child.prototype = new F();
 child.prototype.constructor = child;
 child.pp = parent.prototype;
};

_.extendM = function(className,methodName,extraFunc){

 if(className.pp && className.pp[methodName]){
  className.prototype[methodName] = function(){
   var result = extraFunc.apply(this,arguments);
   className.pp[methodName].apply(this,arguments);
   return result;
  };
 }
 else{
  className.prototype[methodName] = function(){
   return extraFunc.apply(this,arguments);
  };
 }
};
_.trim = function(text){
 if(String.prototype.trim){
  return text == null ?"" :String.prototype.trim.call(text);
 }else{
  return text == null ?"" :text.toString().replace( /^\s+/, "" ).replace(  /\s+$/, "" );
 }
};

_.cookie = function(name,value,options){
  if (typeof value != 'undefined') { 
     options = options || {};
     if (value === null) {
         value = '';
         options.expires = -1;
     }
     var expires = '';
     if (options.expires && (typeof options.expires == 'number' || options.expires.toUTCString)) {
         var date;
         if (typeof options.expires == 'number') {
             date = new Date();
             date.setTime(date.getTime() + (options.expires * 24 * 60 * 60 * 1000));
         } else {
             date = options.expires;
         }
         expires = '; expires=' + date.toUTCString();
     }
     var path = options.path ? '; path=' + options.path : '';
     var domain = options.domain ? '; domain=' + options.domain : '';
     var secure = options.secure ? '; secure' : '';
     document.cookie = [name, '=', encodeURIComponent(value), expires, path, domain, secure].join('');
 } else { 
     var cookieValue = '';
     if (document.cookie && document.cookie != '') {
         var cookies = document.cookie.split(';');
         for (var i = 0; i < cookies.length; i++) {
             var cookie = _.trim(cookies[i]);
          
             if (cookie.substring(0, name.length + 1) == (name + '=')) {
                 cookieValue = decodeURIComponent(cookie.substring(name.length + 1));
                 break;
             }
         }
     }
     return cookieValue;
 }
};