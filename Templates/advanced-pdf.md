<div id="pdfViewer"></div>
<script src="https://cdnjs.cloudflare.com/ajax/libs/pdf.js/2.10.377/pdf.min.js"></script>
<script>
  const url = '../assets/<filename>.pdf';
  
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
