<!--- Section 2 using JavaScript--->

<!--- Q1 --->
for ( var i = 3; i <= 100; i++ ) {
    if ( i % 3 == 0 || i % 5 == 0 ){ 
        document.write(i + "  ");
    }
}

<!--- Q2 --->
function findHCF(num, arr) {
  var posi_arr = [];
  var x = 0;
  //find all positive integer and store in another array
  for ( var i = 0; i < arr.length; i++ ) {
    if ( arr[i] + Math.abs( arr[i] ) != 0 ) { 
      posi_arr.push( arr[i] );
      x++;
    }
    if ( x == num ) {
    	break;
    }
  }	
  //find smallest and start from there
  var smallest = posi_arr[0];
  //if no positive num, return error
  if ( posi_arr.length == 0 ) {
  	return document.write("No positive integers in the array.");
  }
  //if only one element, return the element
  else if ( posi_arr.length == 1 ) {
  	return smallest;
  }
  else {
  //if array length is many, find smallest by comparison
    for ( var i = 0; i < posi_arr.length; i++ ) {
      if ( smallest > posi_arr[i]) { 
        smallest = posi_arr[i];
      }
    }	
  }
  //find HCF
  var found_counter = 0;
  for ( var i = smallest; i >= 1; i--) {
    found_counter = 1;
  	for ( var j = 0; j < posi_arr.length; j++ ) {
      if ( posi_arr[j] % i != 0 ) {
        found_counter = 0;
        break;
      }
    }
    if ( found_counter == 1) {
      return i;
    }
  }
}

<!--- Q3 --->
function palindrome(word) {
  for ( var i = 0; i <= Math.floor(word.length / 2); i++ ) {
  	if ( word[i] != word[word.length - i - 1] ) {
      return "The string is not a palindrome.";
    }
  }
  return "The string is a palindrome.";
}