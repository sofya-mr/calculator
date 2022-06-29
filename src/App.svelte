<script>
	import Button from "./Button.svelte";
	import Numbers from "./Numbers.svelte";
	import Keypad from "./Keypad.svelte";

	let visibleValue = 0;
	let storedValue;
	let isFinished = false;
	let whatToDo;

	function addNumber(event) {
		const num = event.detail; // action or num
		if (typeof num === "number") {
			if(isFinished === true) {
				visibleValue=num;
				isFinished=false;
				return
			}
			
			if (visibleValue) {
				visibleValue = visibleValue * 10 + num * 1;
			} else {
				visibleValue = num;
			};
		} else if (typeof num === "string") {
				switch (num) {
					case 'AC' :
						visibleValue = 0;
						storedValue = 0;
						isFinished = false;
						break
					case '-':
						visibleValue = 0 - visibleValue;
						break
					case '%':
						visibleValue = visibleValue / 100;
						break
				}
			} else {
				isFinished = true;

				if (storedValue) {
					visibleValue = whatToDo(storedValue, visibleValue); //prev operation
				}
				storedValue= visibleValue;

				whatToDo = event.detail; // new operation
			
		}
	}

	

	// function use
	// if (isFinished)
</script>

<div>
	<Numbers value={visibleValue} />
</div>

<div>
	<Keypad on:printNumber={addNumber} />
</div>
