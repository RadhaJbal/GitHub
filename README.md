# GitHub
My Javascript
<!DOCTYPE html>
<html>
	<head>
		<title>Walrus Weights</title>
	</head>
	<body>
		<FORM action="">
   <P>
   <TEXTAREA name="plates" id="plates" cols="4" rows=1000></TEXTAREA>
   <INPUT type="submit" value="Send" onclick="WalrusWgt();">
   </P>
</FORM>	
<script type="text/javascript" language=javascript>
var extra=0, input = [], i, newsumsArr=[], 	maxwgt=0, fndflag=0, inp=[], sumsArr = [];
function WalrusWgt()
	{
		var plates, tmpplates=[], cntPlates;
		var target = 1000;
		var resWgt = 0;
		var prefix=0, inpLen;
		var leastDiff=Number.MAX_VALUE;
		var absfn=Math.abs;
		plates=document.getElementById("plates").innerHTML.replace(/ /g,"");
		inp=plates.split("\n");
		cntPlates=inp[0]-1;
		sumsArr.push(resWgt);
		
		inp = inp.slice(1, cntPlates+2);
		while (cntPlates >= 0) {
			input.push(parseInt(inp[cntPlates],10));
			cntPlates--;
		}
		inp=input.reverse();
		inpLen=inp.length;	
		var absfn=Math.abs;
		for(i=0; i < inpLen; i++) {
			newsumsArr = [];  
			sumsArr.filter(AddArrayElts);
			if (fndflag) {resWgt=target;break;}
			sumsArr = sumsArr.concat(newsumsArr);
		}
		if (resWgt==target) {}
		else if (inpLen==1) {resWgt=inp[0];}
		else {
			var arrBiggerElements = sumsArr.filter(BiggerThan);
			if (arrBiggerElements.length==0) { var nextElement=0}
			else {var nextElement = Math.min.apply(Math, arrBiggerElements);}
			var arrSmallerElements = sumsArr.filter(SmallerThan);
			if (arrSmallerElements.length==0) { var prevElement=0}
			else {var prevElement = Math.max.apply(Math, arrSmallerElements);} 
			if (absfn(1000-prevElement)<absfn(nextElement-1000)) {resWgt=prevElement;}
			else {resWgt=nextElement;}
			} 
		  alert(resWgt);
		 }

function AddArrayElts(inArray) {
	if (inArray<1000)
	{var a=inArray + inp[i];
	if (a==1000){newsumsArr.push(a);fndflag=1;}
	else {
	if (a<1000) newsumsArr.push(a);
	else if (maxwgt==0) maxwgt=a;
	else if (a>1000 && a<maxwgt) {newsumsArr.push(a);
	if (sumsArr.indexOf(maxwgt)>0)
	{sumsArr.splice(sumsArr.indexOf(maxwgt),1);}
	debugger
	maxwgt=a;}
	}
	}
}

function BiggerThan(inArray) {
   return inArray > 1000;
}

function SmallerThan(inArray) {
   return inArray < 1000;
}

</script>
</body>
</html>
