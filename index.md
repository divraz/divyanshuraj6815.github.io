# draj
## Videos of some Interesting Projects
<table>
	<tr>
		<td>
			<iframe src="https://www.linkedin.com/embed/feed/update/urn:li:ugcPost:6629538307233673216" height="500" width="504" frameborder="0" allowfullscreen="" title="Embedded post"></iframe>
		</td>
		<td>
			Training a car to drive on Bangalore roads (Reinforcement Learning)
			<iframe width="560" height="315" src="https://www.youtube.com/embed/wRFr0LPeoyE" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
		</td>
	</tr>
</table>
## Blogs Published on Medium
<table>
	<tr>
		<td>
			<a href="https://medium.com/analytics-vidhya/learn-to-code-in-tensorflow2-fe735ad46826" target="_blank">
				<img src="https://miro.medium.com/max/875/1*Dl6GLvDip8VaUZiTcIl0QA.jpeg" height="200"/>
			</a>
			Data Augmentation with TF2
		</td>
		<td>
			<a href="https://medium.com/@divyanshuraj.6815/learn-to-code-in-tensorflow2-part2-b1c448abbf1e" target="_blank">
				<img src="https://miro.medium.com/max/875/1*FNtUkoKczsNoRFLrY4vRbQ.png" height="200"/>
			</a>
			ResNet18 Model with TF2
		</td>
		<td>
			<a href="https://medium.com/@divyanshuraj.6815/learn-to-code-in-tensorflow2-part3-7664926b9e69" target="_blank">
				<img src="https://miro.medium.com/max/634/1*_b_TQIZbHlwXp9XpmAJfcQ.jpeg" height="200"/>
			</a>
			Training with TF2
		</td>
	</tr>
</table>
<table>
	<tr>
		<td>
			<a href="https://medium.com/@divyanshuraj.6815/not-interested-in-gardening-must-read-for-you-then-982a3bee1025" target="_blank">
				<img src="https://miro.medium.com/max/875/1*tCQAUFjCY14gF5154t8Fow.jpeg" height="200" width="400"/>
			</a>
			Gardening
		</td>
		<td>
			<a href="https://medium.com/@divyanshuraj.6815/stuck-at-nan-not-a-number-while-training-your-model-4b5a6613f87e" target="_blank">
				<img src="https://miro.medium.com/max/875/1*S-OWN1vNP9scaZYV2hXyow.png" height="200"/>
			</a>
			How to get rid of NaN
		</td>
		<td>
			<a href="https://medium.com/analytics-vidhya/relu-activation-increase-accuracy-by-being-greedy-6b93c7c40882" target="_blank">
				<img src="https://miro.medium.com/max/875/1*jqaW5OEqSVF6xjftzRkNnw.jpeg" height="200"/>
			</a>
			Playing with ReLU
		</td>
	</tr>
</table>
## Paintings published on Pinterest
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

## Serverless deployments DEMO
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
