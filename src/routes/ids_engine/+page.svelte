<div class="main-content">
  <h1>Intrusion Detection System</h1>
  <div class="hlayout-spread">
    <div class="hlayout-column">
      <img src="capstone_ss1.jpeg" alt="" />
      <h3 class="tight-header">Overview</h3>
      <p>
        This IDS dashboard allows configuring machine learning algorithms that
        detect malicious networking traffic. In particular, we use classifiers
        from XGBoost, CatBoost, and SciKitLearn combined in different ensembles
        and train them on large network traces. To maximize the classification
        accuracy for particular datasets, hyperparameters can be adjusted to
        tune how the models are trained. The classification performance, along
        with the configuration, is then stored in a local SQLite database to
        allow comparison later. We provide side-by-side comparison between 2
        different configurations to make it easy to see the properties of each
        model. The confusion matrix is a quick summary of expected result vs
        predicted.
      </p>
      <h3 class="tight-header">Technical Info</h3>
      <p>
        I led the implementation of the back-end. Since the machine learning
        models were already implemented using Python, I decided to use Flask.
        The back-end for this project is responsible for all the actual training
        of the models, which included parsing configuration requests from the
        front-end, storing configurations in the database associated with
        particular runs, retrieving past runs, and generating the classification
        performance report to handoff to the front-end.
      </p>
      <p>
        One particularly cool part of this project that sped development up a
        lot was my python documentation parser. In total, there are
        approximately 364 hyperparameters available across the numerous ML
        models, and we felt it was important for usability to allow the user to
        hover over any hyperparameter and understand what it is. Of course,
        manually adding 364 hover hints would be a huge time investment and
        would be error prone. Luckily each library provides extensive
        documentation directly in the source code. I had to write a slightly
        different parser for each library and handle a lots of edge cases
        because each library has a different documentation format, but
        eventually I was able to export every single hyperparameter and import
        them into the database. The end result was that it became much easier to
        use our tuning dashboard and we were able to add this feature way ahead
        of our project deadlines.
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
