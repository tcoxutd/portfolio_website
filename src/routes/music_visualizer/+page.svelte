<div class="main-content">
  <h1>Audio Frequency Spectrum Visualizer</h1>
  <div class="hlayout-spread">
    <div class="hlayout-column">
      <iframe
        width="700px"
        height="432px"
        src="https://www.youtube.com/embed/pZq4pw8kIxQ?si=H_eFVTg6_HV0mOmP"
        title="YouTube video player"
        frameborder="0"
        allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share"
        referrerpolicy="strict-origin-when-cross-origin"
        allowfullscreen
      ></iframe>
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
        dedicated audio thread. 

        The UI includes the ability to pick a song, pause/play controls, playback progress slider, and spectrum zoom/scale.
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
</style>
