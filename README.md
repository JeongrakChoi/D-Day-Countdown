# D-Day-Countdown
D-Day Countdown 디데이 카운트다운


```html
<div id="countdown"></div>
```

```javascript
//카운트다운 함수
function CountDownTimer(dt, id) {
	var end = new Date(dt);
	var _second = 1000;
	var _minute = _second * 60;
	var _hour = _minute * 60;
	var _day = _hour * 24;
	var timer;
 
	function showRemaining() {
		var now = new Date();
		var distance = end - now;

		var days = Math.floor(distance / _day);
		var hours = Math.floor((distance % _day) / _hour);
		var minutes = Math.floor((distance % _hour) / _minute);
		var seconds = Math.floor((distance % _minute) / _second);

		document.getElementById(id).innerHTML = "<span>" + days + "일" + "</span>" +  "<span>" + hours + "시간" + "</span>" + "<span>" + minutes + "분" + "</span>" + "<span>" + seconds + "초" + "</span>";
		
		//시간 종료 시
		if (distance < 0) {
			clearInterval(timer);
			document.getElementById(id).innerHTML = '카운트다운 끝';
			return;
		}
	}	
	timer = setInterval(showRemaining, 1000);
}

//카운트다운 실행
CountDownTimer('12/1/2022', 'countdown'); //기준일 22년 12월 1일
//CountDownTimer('12/1/2022 5:00 PM', 'countdown'); //기준일 22년 12월 1일 5시
```
