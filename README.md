# Kaltura jQuery File Upload Plugin

## Demo
[Demo File Upload](http://kaltura.github.io/jQuery-File-Upload)



## Upstream
For more detailed feature overview see the upstream [JQuery-File-Upload project](https://github.com/blueimp/jQuery-File-Upload)


## Sample Usage
The following will upload files directly to your Kaltura account from the client.
Note that you'll need to [start a Katura Session](http://knowledge.kaltura.com/faq/how-create-kaltura-session) first.
```html
<script src="/js/vendor/jquery.ui.widget.js"></script>
<script src="/js/jquery.fileupload.js"></script>
<script src="/js/jquery.deparam-kaltura.js"></script>
<script src="/js/jquery.fileupload-kaltura.js"></script>
<script type="text/javascript">
  var setupUpload = function() {
    file = $('input[name="fileData"]').fileupload({
      apiURL:'http://www.kaltura.com/api_v3/',
      url: 'http://www.kaltura.com/api_v3/?service=uploadToken&action=upload&format=1',
      ks: client.ks,
      singleFileUploads:true,
      dataType: 'json',
      autoUpload: true,
      done: function(e, data) {
        console.log('fileupload done', e, data);
      },
    });
  };
  $(document).ready(setupUpload);
</script>
<label>Video to Upload</label>
<input type="file" name="fileData">
```
