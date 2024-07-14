For now, the cheat sheet is a nice pdf containing a lot of info. Check the Table of Contents in this tool to navigate through more easily.

![Matt Cone - The Markdown Guide (2018)](<../assets/Matt%20Cone%20-%20The%20Markdown%20Guide%20(2018).pdf>)

<iframe src="../assets/Matt-Cone---The-Markdown-Guide-(2018).pdf" width="100%" height="842" style="border:none;">
    Your browser does not support iframes.
</iframe>

<div id="pdfViewer"></div>
<script src="https://cdnjs.cloudflare.com/ajax/libs/pdf.js/2.10.377/pdf.min.js"></script>
<script>
  const url = '../assets/Matt-Cone---The-Markdown-Guide-(2018).pdf';
  
  const loadingTask = pdfjsLib.getDocument(url);
  loadingTask.promise.then(pdf => {
    console.log('PDF loaded');
    
    // Fetch the first page
    pdf.getPage(1).then(page => {
      console.log('Page loaded');

      const scale = 1.5;
      const viewport = page.getViewport({ scale });

      const canvas = document.createElement('canvas');
      const context = canvas.getContext('2d');
      canvas.height = viewport.height;
      canvas.width = viewport.width;
      document.getElementById('pdfViewer').appendChild(canvas);

      const renderContext = {
        canvasContext: context,
        viewport: viewport,
      };
      page.render(renderContext);
    });

});
</script>
