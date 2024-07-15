**<u>Lab 105</u>** (**<u>Run and interpret evaluation</u>**)

In the previous lab, we configured OpenScale. In this lab, we will configure various model evaluation monitors, and then run an evaluation to calculate these metrics.

1.  **<u>Configure fairness monitors</u>**

    1. From the list of Evaluations on the left, click on fairness.

    2.  Note the description of fairness in the centre of the screen, which gives a good definition of what the monitor is evaluating. Click on the edit icon in the configuration tile.

<img src="./images/media/image1.png" style="width:6.26806in;height:1.97222in" alt="A screenshot of a computer Description automatically generated" />

    3.  You will manually configure the fairness files. Leave configure manually selected and click Next to proceed. To properly monitor a model for unfair bias, you must specify which model outcomes are favourable and which are unfavourable. For our use, favourable class is No Risk and non-favourable class is Risk. Click Next.

<img src="./images/media/image2.png" style="width:6.26806in;height:2.88681in" alt="A screenshot of a computer Description automatically generated" />

    4.  Set the minimum sample size to 50 and click next.

> <img src="./images/media/image3.png" style="width:6.26806in;height:2.48194in" alt="A screenshot of a computer Description automatically generated" />

    5.  Leave the selected monitored metrics set to Disparate impact and click Next.

<img src="./images/media/image4.png" style="width:6.26806in;height:2.48264in" alt="A screenshot of a computer Description automatically generated" />

    6.  Leave the lower and upper thresholds for Disparate impact set to their defaults, and click Next.

<img src="./images/media/image5.png" style="width:6.26806in;height:2.45208in" alt="A screenshot of a computer Description automatically generated" />

    7.  In the next screen, select the fields that you need to monitor for fairness. For now, retain the default values suggested by OpenScale (after analyzing the training data). Click Next.

<img src="./images/media/image6.png" style="width:6.26806in;height:2.53125in" alt="A screenshot of a computer Description automatically generated" />

    8.  In the next screen, select the groups which are to be monitored against the reference group. Here, the percentage of favorable outcomes delivered to the monitored groups will be compared to the percentage of favorable outcomes delivered to the remaining groups (the reference groups) to check for potential bias.

<img src="./images/media/image7.png" style="width:6.26806in;height:2.42361in" alt="A screenshot of a computer Description automatically generated" />

<img src="./images/media/image8.png" style="width:6.26806in;height:2.50347in" alt="A screenshot of a computer Description automatically generated" />

<img src="./images/media/image9.png" style="width:6.26806in;height:2.46389in" alt="A screenshot of a computer Description automatically generated" />

<img src="./images/media/image10.png" style="width:6.26806in;height:2.71319in" alt="A screenshot of a computer Description automatically generated" />

    9.  Use the default alert threshold (80), and click Save to finish configuring the fairness monitor. It may take up to a minute for the configuration to save, at which point you will be returned to the model settings screen.

<!-- -->

2.  **<u>Configure the quality monitor</u>**

    1.  From the list of evaluations on the left, click on Quality.

    2.  Click the edit icon on the Quality thresholds tile.

> <img src="./images/media/image11.png" style="width:6.26806in;height:2.26528in" alt="A screenshot of a computer Description automatically generated" />

    3.  Click the Edit icon on the Quality thresholds tile.

    4.  Leave the default lower and upper threshold values as they are. You can click the Information icon to the right of each value for more information on how it is calculated. Click Next.

<img src="./images/media/image12.png" style="width:6.26806in;height:2.46736in" alt="A screenshot of a computer Description automatically generated" />

    5.  Set the Minimum sample size value to 50. Click Save to save the quality configuration.

<!-- -->

3.  **<u>Configure the explainability service</u>**

    1.  In the Explainability section, click on General settings, and in the explanation method tile, click on the Edit icon.

<img src="./images/media/image13.png" style="width:6.26806in;height:2.49028in" alt="A screenshot of a computer Description automatically generated" />

    2.  Two different methods are available for explanations: Shapley Additive Explanations (SHAP) or Local Interpretable Model-agnostic Explanations (LIME). Toggle the SHAP global explanation to ON, and for local explanation method select LIME.

<img src="./images/media/image14.png" style="width:6.26806in;height:2.41875in" alt="A screenshot of a computer Description automatically generated" />

    3.  Click Next, and for control features go ahead with the default selection (i.e., selected all).

<img src="./images/media/image15.png" style="width:6.26806in;height:2.74583in" alt="A screenshot of a computer Description automatically generated" />

4.  **<u>Configure SHAP</u>**

    1.  To configure SHAP, click the pen icon under common settings.

<img src="./images/media/image16.png" style="width:6.26806in;height:2.20139in" alt="A screenshot of a computer Description automatically generated" />

    2.  For background data select Use training data, and click Save.

<img src="./images/media/image17.png" style="width:6.26806in;height:2.41181in" alt="A screenshot of a computer Description automatically generated" />

5.  **<u>Configure Drift v2</u>**

    1.  Drift is important metric to monitor if the deployments are up-to-date. To configure drift, click on pen under compute the drift archieve.

<img src="./images/media/image18.png" style="width:6.26806in;height:2.29792in" alt="A screenshot of a computer Description automatically generated" />

    2.  For compute option, select Compute in Watson OpenScale.

<img src="./images/media/image19.png" style="width:6.26806in;height:2.43819in" alt="A screenshot of a computer Description automatically generated" />

    3.  For the drift thresholds, retain the default values. Click Next. For minimum sample size, keep 50 and click save.

<img src="./images/media/image20.png" style="width:6.26806in;height:2.44722in" alt="A screenshot of a computer Description automatically generated" />

6.  **<u>Run an evaluation</u>**

    1.  Return to the Insights Dashboard by clicking on the Dashboard link the upper left, and click on the tile for the model you configured (german-credit-risk-testing)

    2.  Click on the Actions button to open the Actions menu, click on Evaluate now.

<img src="./images/media/image21.png" style="width:6.26806in;height:2.52569in" alt="A screenshot of a computer Description automatically generated" />

    3.  Import test data screen pops up, select import from CSV file and then browse the feedback file from your local system, and keep the option of Test data includes output as unchecked.

<img src="./images/media/image22.png" style="width:6.26806in;height:6.77778in" alt="A screenshot of a computer Description automatically generated" />

    4.  Click Upload and evaluate.

After some time, the results of the evaluation can be seen in the dashboard.

7.  **<u>Viewing and interpreting the results</u>**

    1.  Take a moment to review the results of the evaluation. Note that, based on the content of the random sample of the evaluation data, your results will vary each time you perform the evaluation.

    2.  Review the different metrics in the quality table. In the screenshot below, notice that, if the measurement falls below the alert threshold set when you configured the quality monitor, the amount will be listed in the Violation column of the table.

> <img src="./images/media/image23.png" style="width:6.26806in;height:2.80556in" alt="A screenshot of a computer Description automatically generated" />

    3.  Beyond meeting standards for quality and fairness, AI models in many cases are required to provide explanations into the decisions or predictions they make. This can be viewed in watsonx.governance by clicking on the arrow icon in the fairness tile, and then selecting view payload transactions.

<img src="./images/media/image24.png" style="width:6.26806in;height:2.90764in" alt="A screenshot of a survey Description automatically generated" />

<img src="./images/media/image25.png" style="width:6.26806in;height:1.24792in" alt="A screenshot of a computer Description automatically generated" />

    4.  From the table of transactions, click one of the Explain prediction links. The explainability service will use the LIME algorithm to generate a detailed explanation, which can take a few minutes to run.

> <img src="./images/media/image26.png" style="width:6.26806in;height:2.05972in" alt="A screenshot of a group Description automatically generated" />

    5.  Once the explanation has been generated, scroll down to the graph, which shows the influence different features had in the model's outcome. Features in blue increased the final score, while those in red decreased it. For classification models, blue features contributed positively to the model's confidence in the prediction, while those in red decreased the confidence.

> <img src="./images/media/image27.png" style="width:6.26806in;height:2.61806in" alt="A screenshot of a graph Description automatically generated" />

    6.  Click on the Inspect tab. On this tab, you can alter values associated with the record and re-submit it to the model to see how the final risk calculation changes. This can be useful for understanding how the model is working, or if a policyholder is looking for ways to decrease their risk assessment.

> <img src="./images/media/image28.png" style="width:6.26806in;height:2.59722in" alt="A screenshot of a computer Description automatically generated" />

8.  **<u>Approving model for production</u>**

    1.  Return to the Insights Dashboard by clicking on the Dashboard link the upper left, and click on the tile for the model you configured (german-credit-risk-testing)

    2.  Click on the Actions button to open the Actions menu, click on Approve for production now.

<img src="./images/media/image29.png" style="width:6.26806in;height:3.49792in" alt="A screenshot of a computer Description automatically generated" />

    3.  Now, before configuring the production monitoring in the OpenScale, we need to promote our model to a development space. For this, we will repeat step under Section 2 and 3 in Lab 102. Just make sure, while creating new deployment space, select Production as the stage, and rest of the steps remain the same.

    4.  Now, we will create a new machine learning service provider for the production space. Under machine learning providers, fill the name of providers and description, along with connection details. Select service provider as Watson machine learning (v2),

<img src="./images/media/image30.png" style="width:6.26806in;height:2.00347in" alt="A screen shot of a computer Description automatically generated" />

> <img src="./images/media/image31.png" style="width:6.26806in;height:2.50625in" alt="A screenshot of a computer Description automatically generated" />

    5.  Click on the monitor icon to return to the **Insights dashboard**.

<img src="./images/media/image32.png" style="width:6.26806in;height:1.46389in" alt="Return dashboard" />

    6.  Click on the blue **Add to dashboard** button. The **Select a model deployment** screen will open.

<img src="./images/media/image33.png" style="width:6.26806in;height:1.36389in" alt="Add to dashboard" />

    7.  Click on the **Machine learning providers** button.

<img src="./images/media/image34.png" style="width:6.26806in;height:1.62847in" alt="ML providers select" />

    8.  From the list of providers, select the one you are using for this lab (production level ml provider). Click next

> <img src="./images/media/image35.png" style="width:6.26806in;height:1.63333in" alt="A screenshot of a computer Description automatically generated" />

    9.  Select the deployed model. Click next.

<img src="./images/media/image36.png" style="width:6.26806in;height:2.84861in" alt="A screenshot of a computer Description automatically generated" />

    10. In the next provide model information screen, select import settings and click next. This is to import the configuration settings from the pre-production. Click Next.

<img src="./images/media/image37.png" style="width:6.26806in;height:2.84028in" alt="A screenshot of a computer Description automatically generated" />

    11. In the next screen, select the pre-production deployment, and click view summary and finish.

<img src="./images/media/image38.png" style="width:6.26806in;height:1.11806in" alt="A screenshot of a computer Description automatically generated" />

    12. OpenScale production dashboard will show-up with all the metrics that we configured for the pre-production.

<img src="./images/media/image39.png" style="width:6.26806in;height:2.58056in" alt="A screenshot of a computer Description automatically generated" />

    13. Now, we can monitor this production model.

    14. Now, we go back to our dashboard. Click actions, and select evaluate now.

<img src="./images/media/image40.png" style="width:6.26806in;height:2.67639in" alt="A screenshot of a computer Description automatically generated" />

    15. From your data folder, upload payload data, and click evaluate now.

<img src="./images/media/image41.png" style="width:6.26806in;height:2.75347in" alt="A screenshot of a test Description automatically generated" />

After running, you can see results of your evaluations in the dashboard. If you go back to your watsonx.governance AI use case dashboard, you can see these alerts in the model lifecycle.

<img src="./images/media/image42.png" style="width:6.26806in;height:2.97847in" alt="A screenshot of a computer Description automatically generated" />
