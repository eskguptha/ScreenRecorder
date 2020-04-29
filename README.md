# WebScreenRecorder
Record screen activity, camera, mic, tab, speakers in 4K HD video format (using ScreenRecorder)

<button onclick="return start_recording()">Start Recording</button>
<button onclick="return stop_recording()">Stop Recording</button>

<script type="text/javascript">
if(typeof WebScreenRecorderRTC_Extension === 'undefined') {
    alert('WebScreenRecorder chrome extension is either disabled or not installed.');
  }

function start_recording(){
  try{
      recorder = new WebScreenRecorderRTC_Extension();
        rec_options = {
            enableScreen: true,
            enableMicrophone: true,
            enableSpeakers: true
          }
      recorder.startRecording(rec_options, function() {});
    }
    catch(ex){
      console.log(ex.message);
    }
  }
function stop_recording(){
    try{
        recorder.setVideoFileName({"video_file_name": "2020-04-32"});
        recorder.stopRecording(function(blob) {
        });  
      }
      catch(ex){
        console.log(ex.message);
      }
  };
  </script>
