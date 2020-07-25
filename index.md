<p><input type="file"  accept="image/*" name="image" id="file"  onchange="loadFile(event)" style="display: none;"></p>
<p><label for="file" style="cursor: pointer;">Upload Image</label></p>
<p><img id="output" width="200" /></p>
<p><li id="mobilenet_error"></li></p>
<p><li id="mobilenet_pred"></li></p>

<script>
var loadFile = function(event) {
	var image = document.getElementById('output');
	image.src = URL.createObjectURL(event.target.files[0]);
    console.log (event.target.files[0]);
	document.getElementById("mobilenet_error").innerHTML = "Fetching results for MobileNet V2....."
	
	fetch("https://ie8mujag6h.execute-api.ap-south-1.amazonaws.com/dev/classify", { 
      method: "POST", 
      body: event.target.files[0],
      headers: { 
          "content-type": "multipart/form-data"
      } 
	}) 
	.then(response => response.json()) 
	.then(json => {
		console.log (json);
		document.getElementById("mobilenet_error").innerHTML = json.error;
        document.getElementById("mobilenet_pred").innerHTML = json.predicted}); 
};
</script>
