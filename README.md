# Bookies
"Style css" code below
h1 {
	text-align: center;
}

form {
	display: flex;
	flex-direction: column;
	align-items: center;
	margin-top: 20px;
}

label {
	margin-top: 10px;
}

select {
	margin-left: 10px;
	margin-right: 10px;
}

input[type="submit"] {
	margin-top: 20px;
}

#result {
	margin-top: 20px;
	font-weight: bold;
	text-align: center;
} 
JavaScript" code below saved as "converter.js"

const form = document.querySelector('form');
const resultDiv = document.querySelector('#result');

form.addEventListener('submit', (event) => {
	event.preventDefault();

	const betCodeInput = document.querySelector('#bet-code');
	const targetFormatSelect = document.querySelector('#target-format');
	const conversionPointsInput = document.querySelector('#conversion-points');

	const betCode = betCodeInput.value;
	const targetFormat = targetFormatSelect.value;
	const conversionPoints = parseInt(conversionPointsInput.value, 10);

	if (isNaN(conversionPoints) || conversionPoints <= 0) {
		alert('Invalid conversion points');
		return;
	}

	let convertedBetCode = '';

	switch (targetFormat) {
 case 'sportybet':
			convertedBetCode = convertToSportyBet(betCode, conversionPoints);
			break;
		case 'bet9ja':
			convertedBetCode = convertToBet9ja(betCode, conversionPoints);
			break;
		case 'betking':
			convertedBetCode = convertToBetKing(betCode, conversionPoints);
			break;
		default:
			alert('Invalid target format');
			return;
	}

	resultDiv.textContent = `Converted bet code: ${convertedBetCode}`;
});

function convertToSportyBet(betCode, conversionPoints) {
	// TODO: Implement conversion logic for SportyBet format
	return '';
}

function convertToBet9ja(betCode, conversionPoints) {
	// TODO: Implement conversion logic for Bet9ja format
	return '';
}

function convertToBetKing(betCode, conversionPoints) {
	// TODO: Implement conversion logic for BetKing format
	return '';
}
