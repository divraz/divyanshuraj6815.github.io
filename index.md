<table>
  <td>
    <table>
      <tr>
        <td>
          <input type="file" id="imageUpload" onchange="loadFile(event)"/>
        </td>
      <tr>
        <td>
          <img id="output" width="200" />
        </td>
      </tr>
    </table>
  </td>
  <td>
    <table>
      <tr>
        <li id="mobilenet_custom">MobileNet V2 (Winged Drones, Flying Birds, Quadcopters)</li>
        <li id="mobilenet_imagenet">MobileNet V2 (ImageNet 1000 Classes)</li>
      </tr>
    </table>
  </td>
</table>

<script>
  var loadFile = function(event) {
	var image = document.getElementById('output');
  const files = event.target.files
	
  image.src = URL.createObjectURL(files[0]);
  document.getElementById("mobilenet_custom").innerHTML = "Fetching results....."

  const formData = new FormData ();
  formData.append ("data", files[0]);
  console.log (formData);
   
	fetch("https://ie8mujag6h.execute-api.ap-south-1.amazonaws.com/dev/classify", {
    method: "POST",
    body: formData,
  })
	.then(response => response.json())
	.then(json => {
	  console.log (json);
      if (json.error) {
			  document.getElementById("mobilenet_custom").innerHTML = json.error;
      } else {
       	document.getElementById("mobilenet_custom").innerHTML = json.predicted[1];
      }   
   });
   
  document.getElementById("mobilenet_imagenet").innerHTML = "Fetching results....."
  fetch("https://flte7grm73.execute-api.ap-south-1.amazonaws.com/dev/classify", {
    method: "POST",
    body: formData,
  })
	.then(response => response.json())
	.then(json => {
	  console.log (json);
      if (json.error) {
			  document.getElementById("mobilenet_imagenet").innerHTML = json.error;
      } else {
       	document.getElementById("mobilenet_imagenet").innerHTML = json.predicted[1];
      }   
   });

};
</script>
