MooTools Canvas Library
===========

This library provides functionality to manage and interact with the content of a html5 canvas element. It emulates layers and items that can be manipulated and managed and provides mouse-events to the items. 

[Documentation](http://forvar.de/js/mcl/docs.CANVAS.html)
[Examples/Demos](http://forvar.de/js/mcl/examples.html)

How to use
----------

Initialize the CANVAS-object, then start adding layers, items and threads:

	#HTML
	<canvas height="400" width="600" id="DOMCanvasElement"></canvas>


	#JS
	CANVAS.init({ canvasElement : 'DOMCanvasElement' });
	CANVAS.layers.add( new Layer({ id : 'myLayer' });
	CANVAS.layers.get('myLayer').add( new CanvasItem({
		id : 'myItem',
		x : 100,
		y : 100,
		events : {
			onDraw : function(ctx){
				this.x++;
				this.y++;
				ctx.fillStyle = '#000';
				ctx.fillRect(this.x,this.y,50,50);
			}
		}
	}));
	CANVAS.addThread( new Thread({ 
		id : 'myThread',
		onExec : function()
		{
			CANVAS.clear().draw();
		}
	}) );
