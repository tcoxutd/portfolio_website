<div class="main-content">
  <h1>Art Commission Tracker App</h1>
  <a href="https://github.com/nice-sprite/CommsApp">GitHub</a>
  <div class="hlayout-spread">
    <div class="hlayout-column">
      <div class="hlayout-spread constrain-img-width">
        <div class="hlayout-column layout_img ">
            <img src="/comm_app1.jpg" alt="" class="img1">
        </div>
        <div class="hlayout-column layout_img ">

            <img src="/comm_app_add.jpg" alt="" class="img1">
        </div>
        <div class="hlayout-column layout_img ">
            
            <img src="/comm_app_mark_finished.jpg" alt="" class="img1">
        </div>
        <div class="hlayout-column layout_img ">
            
            <img src="/comm_app_updated_money.jpg" alt="" class="img1">
        </div>
      </div>

      <h3 class="tight-header">Overview</h3>
      <p>
        This is a audio visualizer featuring an oscilloscope and a spectrogram.
        The oscilloscope shows the waveform in real-time as the audio buffer is
        decoded and sent to the sound driver. The spectrogram, aka spectrum
        analyzer, plots the amplitude of each frequency in the song.
      </p>
      <h3 class="tight-header">Technical Info</h3>
      <p>
        This project is written in Rust, and uses WGPU along with Dear ImGui for
        displaying the spectrum. The UI updates in its own thread and simply
        pulls from a ring buffer of audio samples, which is filled by the
        dedicated audio thread. The UI includes the ability to pick a song,
        pause/play controls, playback progress slider, and spectrum zoom/scale.
      </p>
    </div>
  </div>
</div>

<style>
  p {
    text-align: left;
    width: 80%;
    max-width: 1000px;
  }

  h3 {
    text-align: left;
  }

  .layout_img {
    margin: 0.2em;
  }

  .img1 {
    background-color: aliceblue;
    max-width: 100%;
    max-height: 1000px;
  }
  
  .constrain-img-width {
    max-width: 80%;
  }
</style>
