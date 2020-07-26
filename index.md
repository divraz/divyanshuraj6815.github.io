<table>
	<tr>
		<td>
			<iframe src="https://www.linkedin.com/embed/feed/update/urn:li:ugcPost:6629538307233673216" height="500" width="504" frameborder="0" allowfullscreen="" title="Embedded post"></iframe>
		</td>
		<td>
			<iframe width="560" height="315" src="https://www.youtube.com/embed/wRFr0LPeoyE" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
		</td>
	</tr>
</table>
<table>
	<tr>
		<td>
			<a href="https://medium.com/analytics-vidhya/learn-to-code-in-tensorflow2-fe735ad46826" target="_blank">
				<img src="https://miro.medium.com/max/875/1*Dl6GLvDip8VaUZiTcIl0QA.jpeg" height="300"/>
			</a>
		</td>
		<td>
			<a href="https://medium.com/@divyanshuraj.6815/learn-to-code-in-tensorflow2-part2-b1c448abbf1e" target="_blank">
				<img src="https://miro.medium.com/max/875/1*FNtUkoKczsNoRFLrY4vRbQ.png" height="300"/>
			</a>
		</td>
		<td>
			<a href="https://medium.com/analytics-vidhya/learn-to-code-in-tensorflow2-fe735ad46826" target="_blank">
				<img src="https://miro.medium.com/max/875/1*Dl6GLvDip8VaUZiTcIl0QA.jpeg" height="300"/>
			</a>
		</td>
	</tr>
</table>
<table>
	<tr>
		<td>
			<iframe src="https://assets.pinterest.com/ext/embed.html?id=763782418041109141" height="597" width="345" frameborder="0" scrolling="no" ></iframe>
		</td>
		<td>
			<iframe src="https://assets.pinterest.com/ext/embed.html?id=763782418041109034" height="612" width="345" frameborder="0" scrolling="no" ></iframe>
		</td>
		<td>
			<iframe src="https://assets.pinterest.com/ext/embed.html?id=763782418041109181" height="675" width="345" frameborder="0" scrolling="no" ></iframe>
		</td>
	</tr>
	<tr>
		<td>
			<iframe src="https://assets.pinterest.com/ext/embed.html?id=763782418041109125" height="520" width="345" frameborder="0" scrolling="no" ></iframe>
		</td>
		<td>
			<iframe src="https://assets.pinterest.com/ext/embed.html?id=763782418041109155" height="560" width="345" frameborder="0" scrolling="no" ></iframe>
		</td>
		<td>
			<iframe src="https://assets.pinterest.com/ext/embed.html?id=763782418041109044" height="560" width="345" frameborder="0" scrolling="no" ></iframe>
		</td>
	</tr>
	<tr>
		<td>
			<iframe src="https://assets.pinterest.com/ext/embed.html?id=763782418041109016" height="469" width="345" frameborder="0" scrolling="no" ></iframe>
		</td>
		<td>
			<iframe src="https://assets.pinterest.com/ext/embed.html?id=763782418041109191" height="574" width="345" frameborder="0" scrolling="no" ></iframe>
		</td>
		<td>
			<iframe src="https://assets.pinterest.com/ext/embed.html?id=763782418041108993" height="359" width="345" frameborder="0" scrolling="no" ></iframe>

		</td>
	</tr>
</table>
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
	      <li>First time might fail due to warm start, please try again</li>
        <li id="mobilenet_custom">MobileNet V2 (Winged Drones, Flying Birds, Quadcopters)</li>
        <li id="mobilenet_imagenet">MobileNet V2 (ImageNet 1000 Classes)</li>
      </tr>
    <iframe src="https://medium.com/analytics-vidhya/learn-to-code-in-tensorflow2-fe735ad46826" name="myFrame"></iframe>
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
