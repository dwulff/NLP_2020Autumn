---
layout: page
title: Schedule & Materials
---

<style>
e {
  font-size: 1.5em;
  font-weight: 900;
}
</style>

## 15.09.

<e>Intro</e>

- Presentation: <a href="https://dwulff.github.io/NLP_2020Autumn/assets/key/Intro.pdf">Intro.pdf</a>

## 22.09.

<e>Tokenization & Markdown</e>

- Preparation: Complete <a href="menu/installation"><b>installation</b></a> instructions incl. swirl
- Presentation: <a href="https://dwulff.github.io/NLP_2020Autumn/assets/sessions/Tokenization/Tokenization_intro.html">Tokenization</a>, <a href="https://dwulff.github.io/NLP_2020Autumn/assets/sessions/Tokenization/Markdown_intro.html">Markdown</a>
- Assignment: <a href="https://dwulff.github.io/NLP_2020Autumn/assets/sessions/Tokenization/Tokenization.html">Tokenization</a>

<div id="filesubmit">
  <input type="file" class="file-select" accept="image/*"/>
  <button class="file-submit">SUBMIT</button>
</div>

## 29.09.

<e>Zipf's law</e>

- Preparation: Read <a href="https://dwulff.github.io/NLP_2020Autumn/assets/pdf/Piantadosi2014.pdf">Piantadosi (2014)</a>
- Presentation:
- Assignment:

## 06.10.

<e>Tidytext</e>

- Presentation:
- Assignment:

<!---Doodle--->

## 13.10.

<e>Semantics</e>

- Preparation: Read <a href="https://dwulff.github.io/NLP_2020Autumn/assets/pdf/Bullinaria&Levy2007.pdf">Bullinaria & Levy (2007)</a>
- Presentation:
- Assignment:

## 20.10.

<e>Sentiment</e>

- Preparation: Read <a href="https://dwulff.github.io/NLP_2020Autumn/assets/pdf/Reagan2016.pdf">Reagan (2016)</a>
- Presentation:
- Assignment:

## 27.10.

<e>Project proposals</e>

## 27.10. - 24.11.

<e>Project work & meetings</e>

## 24.11.

<e>Markdown presentations</e>

## 24.11. - 15.12.

<e>Project work & meetings</e>

## 15.12.

<e>Final presentations</e>


<!-- The core Firebase JS SDK is always required and must be listed first -->
<script src="https://www.gstatic.com/firebasejs/7.21.0/firebase-app.js"></script>

<!-- TODO: Add SDKs for Firebase products that you want to use
     https://firebase.google.com/docs/web/setup#available-libraries -->
<script src="https://www.gstatic.com/firebasejs/7.21.0/firebase-analytics.js"></script>

<script>
  // Your web app's Firebase configuration
  // For Firebase JS SDK v7.20.0 and later, measurementId is optional
  var firebaseConfig = {
    apiKey: "AIzaSyCk7sxXUul8G6DYOWg8cNfg3iD9yuqgLxU",
    authDomain: "rationality-4f945.firebaseapp.com",
    databaseURL: "https://rationality-4f945.firebaseio.com",
    projectId: "rationality-4f945",
    storageBucket: "rationality-4f945.appspot.com",
    messagingSenderId: "607256678766",
    appId: "1:607256678766:web:f606568075c7c8cfa4717f",
    measurementId: "G-N4CB32MRHN"
  };
  // Initialize Firebase
  firebase.initializeApp(firebaseConfig);
  firebase.analytics();

  const storageService = firebase.storage();
  const storageRef = storageService.ref();

  document.querySelector('.file-select).addEventListener('change', handleFileUploadChange);
  document.querySelector('.file-submit).addEventListener('click', handleFileUploadSubmit);

  let selectedFile;
    handleFileUploadChange(e) {
      selectedFile = e.target.files[0];
    }

    handleFileUploadSubmit(e) {
    const uploadTask = storageRef.child(`images/${selectedFile.name}`).put(selectedFile); //create a child directory called images, and place the file inside this directory
    uploadTask.on('state_changed', (snapshot) => {
    // Observe state change events such as progress, pause, and resume
    }, (error) => {
      // Handle unsuccessful uploads
      console.log(error);
    }, () => {
       // Do something once upload is complete
       console.log('success');
    });
  }
</script>
