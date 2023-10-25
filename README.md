# Signup-form
I have a Cloud Page with a Sign up form. The Smart capture form works as intended and stores the information into a specific Object.


%%[
var @name, @email, @CountryCode, @contactNumber, @organization, @areaOfInterests, @NumberofEmployees, @Description, @createLead

if RequestParameter("submitted") == true then
  set @name = RequestParameter("Name")
  set @email = RequestParameter("Email")
  set @CountryCode = RequestParameter("country-code")
  set @contactNumber = RequestParameter("Contact_Number")
  set @organization = RequestParameter("Organization")
  set @areaOfInterests = RequestParameter("Area_of_intrests")
  set @NumberofEmployees = RequestParameter("Number_of_employees")
  set @Description = RequestParameter("Description")
  
 set @createLead = CreateSalesforceObject(
    "Lead", 8,
    "LastName", @name,
    "Company", @organization,
    "Email", @email,
    "CountryCode", @CountryCode,
    "Phone", @contactNumber,
     "Area_of_interests__c", @areaOfInterests,
     "Number_of_employees__c", @NumberofEmployees,
     "LeadSource", "Marketingcloud",
     
    "Description__c", @Description
  ) 
  Redirect("https://google.com")
 
endif
]%%

%%=v(@createLead)=%%



  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1, maximum-scale=1, user-scalable=0">
  <title></title>
  <meta name="ROBOTS" content="INDEX,FOLLOW">
  <meta name="keywords" content="">
  <meta name="description" content="">
  <link rel="stylesheet" href="https://maxcdn.bootstrapcdn.com/bootstrap/3.3.7/css/bootstrap.min.css">
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/bootstrap-datetimepicker/4.17.47/css/bootstrap-datetimepicker.min.css">


 <style>
    body {
      color: #000000;
      font-family: "Copperplate", Arial;
      font-size: 12px;
      margin: 0 auto;
      padding: 0;
      background-color:white;
    }
    .container {
      display: flex;
      justify-content: center;
      align-items: center;
      height: 100vh;
    }
    .form-container {
      max-width: 860px;
      text-align: center;
      padding: 20px;
      background-color: #F5921D;
      border-radius: 10px;
    }
    .form-container h2 {
      font-size: 28px;
      color: black;
      font-weight: 800;
      margin-bottom: 10px;
       margin-top: 35px;
    }
    .form-container input[type="text"],
    .form-container input[type="email"],
    .form-container select {
      width: 100%;
      height: 50px;
      outline: none;
      border: 1px solid #ccc;
      border-radius: 5px;
      padding-left: 15px;
      margin-bottom: 20px;
    }
    .form-container textarea {
      width: 100%;
      height: 100px;
      outline: none;
      border: 1px solid #ccc;
      border-radius: 5px;
      padding-left: 15px;
      margin-bottom: 10px;
      font-size: 14px;
      margin-top: 10px;
    }
    .form-container button {
      border: none;
      background-color:#F5921D;
      color: #FFFFFF;
      font-size: 15px;
      font-weight: 690;
      padding: 16px 32px;
      border-radius: 35px;
      cursor: pointer;
        margin-bottom: 35px;
      margin-top: 20px;
    }
  </style>


  <div class="container">
    <div class="form-container">
      <h2>Get In Touch With Us</h2>
      <form action="%%=RequestParameter('PAGEURL')=%%" method="post">
        <div class="row">
          <div class="mobile-margin form-group col-sm-12 col-md-6" style="text-align:left; margin: 10px 0;"> 
            <div class="user-input-wrp">
              <input class="inputText form-control" onkeyup="this.setAttribute('value', this.value);" type="text" id="Name" name="Name" value="" data-error="Name is required" placeholder="Name*" required="">
              <div class="help-block with-errors"></div>
            </div>
          </div>
          <div class="mobile-margin form-group col-sm-12 col-md-6" style="text-align:left; margin: 10px 0;"> 
            <div class="user-input-wrp">
              <input class="inputText form-control" onkeyup="this.setAttribute('value', this.value);" type="email" id="Email" name="Email" value="" pattern="[a-zA-z0-9._%+-]+@[a-zA-z0-9.-]+\.[a-zA-z0-9]{2,}$" data-error="Please enter a valid email address" placeholder="Email*" required="">
              <div class="help-block with-errors"></div>
            </div>
          </div>
        </div>
        <div class="row">
          <div class="mobile-margin form-group col-sm-12 col-md-6" style="text-align:left; margin: 13px 0;"> 
            <div class="user-input-wrp" style="display: flex;">
              <select id="country-code" name="country-code" class="inputText form-control" style="flex:1; max-width:32%;" required="">
                <option value="+1">+1</option>
                <option value="+44">+44</option>
                <option value="+91">+91</option>
                <option value="+93">+93</option>
                <option value="+880">+880</option>
                <option value="+86">+86</option>
                <option value="+20">+20</option>
                <option value="+33">+33</option>
                <option value="+81">+81</option>
                <option value="+60 ">+60 </option>
                <option value="+64">+64</option>
                <option value="+850">+850</option>
                <option value="+7">+7</option>
                <option value="+263">+263</option>
              </select>
              <input class="inputText form-control" onkeyup="this.setAttribute('value', this.value);" type="text" pattern="[789][0-9]{9}" id="ContactNumber" name="Contact_Number" value="" data-error="Contact Number is required" style="flex: 2; max-width: 100%;" placeholder="Contact Number" required="">
            </div>
            <div class="help-block with-errors"></div>
          </div>
           
          <div class="mobile-margin form-group col-sm-12 col-md-6" style="text-align:left; margin: 10px 0;"> 
            <div class="user-input-wrp">
              <input class="inputText form-control" onkeyup="this.setAttribute('value', this.value);" type="text" id="Organization" name="Organization" value="" data-error="Organization is required" placeholder="Organization" required="">
              <div class="help-block with-errors"></div>
            </div>
          </div>
        </div>
        <input class="inputText form-control" onkeyup="this.setAttribute('value', this.value);" type="text" id="Employees" name="Number_of_employees" value="" data-error="Number of Employees is required" placeholder="Number of Employees" required="">
        <select id="Services" name="Area_of_intrests" required="">
          <option value="" disabled="" selected="">Area of interests</option>
          <option value="Salesforce Implementation">Salesforce Implementation</option>
          <option value="CPQ Implementation">CPQ Implementation</option>
          <option value="Cloud Integration">Cloud Integration</option>
          <option value="Cloud on-premise Integration">Cloud on-premise Integration</option>
          <option value="Hybrid Applications">Hybrid Applications</option>
          <option value="Adminified">Adminified</option>
          <option value="Data Migration">Data Migration</option>
          
        </select>
        
        <textarea rows="5" cols="40" name="Description" placeholder="Tell us more" spellcheck="false" style="width: 100%;"></textarea>
      
        
        <input type="hidden" name="submitted" value="true">
        <center>
          <button type="submit" class="button button1" style="background-color: black; font-size: 15px; color: white; font-weight: 690; margin-top: 20px;">Continue to Website &#8594;</button>
        </center> 
      </form>
    </div>
  </div>

  <script src="https://code.jquery.com/jquery-3.3.1.min.js"></script>
  <script src="https://maxcdn.bootstrapcdn.com/bootstrap/3.3.7/js/bootstrap.min.js"></script>
  <script src="https://cdnjs.cloudflare.com/ajax/libs/moment.js/2.22.2/moment.min.js"></script>
  <script src="https://cdnjs.cloudflare.com/ajax/libs/bootstrap-datetimepicker/4.17.47/js/bootstrap-datetimepicker.min.js"></script>
