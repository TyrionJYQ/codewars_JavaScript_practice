### Instructions ###

Check to see if a string has the same amount of 'x's and 'o's. The method must return a boolean and be case insensitive. The string can contains any char.

### Examples input/output: ###


    XO("ooxx") => true
	XO("xooxx") => false
	XO("ooxXm") => true
	XO("zpzpzpp") => true // when no 'x' and 'o' is present should return true
	XO("zzoo") => false


### Sample Tests: ###

    Test.assertEquals(XO('xo'),true);
    Test.assertEquals(XO("xxOo"),true);
    Test.assertEquals(XO("xxxm"),false);
    Test.assertEquals(XO("Oo"),false);
    Test.assertEquals(XO("ooom"),false);


### my solution ###

	function XO(str) {
	    let arr = str.split('');
	    let arr_o = [];
	    let arr_x = [];
	    arr.forEach( (item)=> {
	       if(item === 'o' || item === 'O') {
	          arr_o.push(item);
	        }else if(item === 'x' || item === 'X') {
	          arr_x.push(item);
	        }
	    })
	    return arr_o.length === arr_x.length;
	}