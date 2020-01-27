in order to use  the forms in steps all you got to do is surround your html with steps you need *example*:

    <form>
        <!-- Step 1 -->
                 <div id="step_1">    
            	     <label for="fname">First name</label>  
            	     <input type="text" id="fname" name="fname" placeholder="First name">  
            	     <span id="fnameMsg"></span>      
                </div> 
        <!-- Step 2 -->
                 <div id="step_2">    
            	     <label for="lname">Last name</label>  
            	     <input type="text" id="lname" name="lname" placeholder="Last name">  
            	     <span id="lnameMsg"></span>      
                </div>   
         <!-- Step 3 -->
             <div id="step_3">    
            	     <label for="otherName">Other  name</label>  
            	     <input type="text" id="otherName" name="otherName" placeholder="Othername">  	  
                </div>  
    </form>

and as for  the j-query (this uses my [validation library](https://github.com/kunz398/Custom-FrontEnd-Validation) so make sure to see that documentation before using this)
all you need to pass is the validations and the maximum steps in your form
*Example*

    <script>  
      let max = 3;  
      let validationJson = '{"validationJson":[' +  
      '{"id":"fname","msg":"fnameMsg","valdationType":"required|min:2|alpha","step":"1" },' +  
      '{"id":"lname","msg":"lnameMsg","valdationType":"required|min:2|alpha","step":"2" }' +  
      ']}';  
      formSteps(max, validationJson);  
      
      $('#finshStep').on('click', function (e) {  
	     e.preventDefault();  
	     alert("Done, Ready for Form Submission");  
      });  
    </script>

