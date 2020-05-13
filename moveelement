function getWidth() { return window.innerWidth || document.documentElement.clientWidth || document.body.clientWidth; }
function getLeft() { return document.body.scrollLeft; }
function setLeft(v) { document.body.scrollLeft = v; }
function getScrollbarSize() {
  var div, width;
  div = document.createElement('div');
  div.innerHTML = '<div style="width:50px;height:50px;position:absolute;left:-50px;top:-50px;overflow:auto;"><div style="width:1px;height:100px;"></div></div>';
  div = div.firstChild;
  document.body.appendChild(div);
  width = div.offsetWidth - div.clientWidth;
  document.body.removeChild(div);
  return width;
};

(function(t,w,l,l2) {
  
  document.querySelector('.container').style.height = 'calc(100vh - ' + getScrollbarSize() + 'px)';
  
  w = getWidth(), l = w, l2 = l / w, setLeft(w);
  
  window.addEventListener("resize", function(e) {
    if ( !t ) {
      t = setTimeout(function() {
        t = null;
        resizeHandler(e);
      }, 66);                  /*  throttle timeout  */
    }
  }, false);
  
  function resizeHandler(e) {
    w = getWidth();
    l = getLeft();
    setLeft(w * l2);
  }

  window.addEventListener("scroll", function(e) {
    if ( !t ) {
      l2 = getLeft() / w;
    }
  }, false);
  
}());
