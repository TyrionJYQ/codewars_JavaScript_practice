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


### the  better solutions  others done ###


**use RegExp**

    function XO(str) {
      let x = str.match(/x/gi);
      let o = str.match(/o/gi);
      return (x && x.length) === (o && o.length);
    }

----------

	function XO(str) {
	    var a = str.replace(/x/gi, ''),
	        b = str.replace(/o/gi, '');
	    return a.length === b.length;
	}


**use filter**

    const XO = str => {
    	str = str.toLowerCase().split('');
	    return str.filter(x => x === 'x').length === str.filter(x => x === 'o').length;
	}

**use count to judge**

	function XO(str) {
	  var sum = 0;
	  for(var i=0; i<str.length; i++){
	    if(str[i].toLowerCase() == 'x') sum++;
	    if(str[i].toLowerCase() == 'o') sum--;
	  }
	  return sum == 0;
	}


**mygod**

    var XO=s=>![...s].reduce((t,v)=>t+((v=(v.charCodeAt()-24)%32)?v-23?0:-1:1),0)