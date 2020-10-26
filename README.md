import flash.events.MouseEvent;
import flash.media.SoundChannel;

import flash.events.Event;


var n: int = 0;

txt.text = "Shots the cokes,as fast as you can!";

var timer: Number = 0;

var m: Number;

function f_m() {
	
	timer += 10 / 1000;
	
	if (timer < 10) {
		txt.text = "Left：" + n + "Cokes, Spending" + String(timer).substr(0, 4) + "Second";
	} else if (timer >= 10 && timer < 100) {
		txt.text = "Left：" + n + "Cokes, Spending" + String(timer).substr(0, 5) + "Second";
	} else {
		txt.text = "Left：" + n + "Cokes, Spending" + String(timer).substr(0, 6) + "Second";
	}
	
	
}

var a: A = new A();
var sounda: SoundChannel;

var b: B = new B();
var soundb: SoundChannel;


soundb = b.play();

soundb.addEventListener(Event.SOUND_COMPLETE, f_soundb);
function f_soundb(e: Event) {
	soundb = b.play();
	soundb.addEventListener(Event.SOUND_COMPLETE, f_soundb);
}


bn.addEventListener(MouseEvent.CLICK, f_bn);
function f_bn(e: MouseEvent) {
	for (var i: int = 1; i <= 3; i++) {
		var ball: BALL = new BALL();
		ball.x = stage.stageWidth / 2;
		
	
	ball.y = stage.stageHeight / 2;
		
		
		
	stage.addChild(ball);
		n++;
	if (timer < 10) {
		txt.text = "Left：" + n + "Cokes, Spending" + String(timer).substr(0, 4) + "Second";
	} else if (timer >= 10 && timer < 100) {
		txt.text = "Left：" + n + "Cokes, Spending" + String(timer).substr(0, 5) + "Second";
	} else {
		txt.text = "Left：" + n + "Cokes, Spending" + String(timer).substr(0, 6) + "Second";
	}
	}
	bn.x = -2000;
	timer = 0;
	m = setInterval(f_m, 10);
}



stage.addEventListener(MouseEvent.CLICK, f_stage);
function f_stage(e: MouseEvent) {
	if (e.target is BALL) {
		
		
		
		sounda = a.play();
		
		e.target.gotoAndStop(2);
		n--;
	if (timer < 10) {
		txt.text = "Left：" + n + "Cokes, Spending" + String(timer).substr(0, 4) + "Second";
	} else if (timer >= 10 && timer < 100) {
		txt.text = "Left：" + n + "Cokes, Spending" + String(timer).substr(0, 5) + "Second";
	} else {
		txt.text = "Left：" + n + "Cokes, Spending" + String(timer).substr(0, 6) + "Second";
	}

		
		
		if (e.target.width >= 30) {
			for (var i: int = 1; i <= 3; i++) {
				
				var ball: BALL = new BALL();
				
				ball.x = e.target.x;
				
				ball.y = e.target.y;
				
				ball.width  = e.target.width / 2;
				
				
				
				
				
				ball.height = e.target.height / 2;
				
				
				
				
				
				
				
				stage.addChild(ball);
				
				
				
				
				n++;
		if (timer < 10) {
		txt.text = "Left：" + n + "Cokes, Spending" + String(timer).substr(0, 4) + "Second";
	} else if (timer >= 10 && timer < 100) {
		txt.text = "Left：" + n + "Cokes, Spending" + String(timer).substr(0, 5) + "Second";
	} else {
		txt.text = "Left：" + n + "Cokes, Spending" + String(timer).substr(0, 6) + "Second";
	}
			}
		}
		if (n <= 0) {
			bn.x = stage.stageWidth / 2;
			n = 0;
			
			
			clearInterval(m);
			
			
			if(timer < 10) {
			txt.text = "Congratulation,You Finished! Spending" + String(timer).substr(0, 4) + "Sec。";
		} else if (timer >= 10 && timer < 100) {
			txt.text = "Congratulation,You Finished! Spending" + String(timer).substr(0, 5) + "Sec。";
		} else { 
			txt.text = "Congratulation,You Finished! Spending" + String(timer).substr(0, 6) + "Sec。";
		}
			
		}
	}
}
