# Troubleshooting Tips for Labs 1 and 2

If you are running into some issues related to disabled access, unclickable buttons, not being able to view things in the instructions, etc., please refer to these tips below. 

If you want to add to this list, please create a GitHub `Issue` or notify the repo's contributors!

## Table of Contents
1. [I'm not able to run an evaluation job.](#1)
2. [I can't find the correct class instance anywhere.](#2)
3. [I can't select any dimensions to evaluate.](#3)
4. [watsonx Challenge](#4)

## I'm not able to run an evaluation job.<a name="1"></a>
Check to make sure you are on the correct cloud instance for this class. You will not have the same capabilities in the labs using your personal account (see below).

![evaluate](./lab1-assisted-prompt-evaluation/images/evaluate.png)

Go to the top right of the screen, click the dropdown menu, and switch to the correct instance for the class. The instructor should've share with you the correct instance. For example, my class instance is called *2567338 - itztsccprojects10*.

![select-instance](./lab1-assisted-prompt-evaluation/images/select-instance.png)

## I can't find the correct class instance anywhere.<a name="2"></a>
If the instructors provided you a class instance that doesn't appear in the lists of instances in cloud.ibm.com, 
1. Try switching to a Google Chrome browser to work on the labs, as switching has resolved the issue for some.
2. Otherwise, check that you received an email from no-reply@cloud.ibm.com inviting you to join the instance. You should receive an email of similar format below. To see the instance in your account, you must click `Join now`.

![cloud-email](./lab1-assisted-prompt-evaluation/images/cloud-email.png)
 
3. If you don't receive that email, consult your instructor.

## I can't select any dimensions to evaluate.<a name="3"></a>

![select-dimensions](./lab1-assisted-prompt-evaluation/images/select-task.png)

Make sure when saving your prompt (Step 3.3 in Lab 1) that you select a task from the drop down menu. If you do not see the task dropdown when saving, make sure you are on the right instance (see [here](#1)), then
1. Create a new prompt.
2. Turn `AI guardrails on` on (top left).

![ai-guardrails](./lab1-assisted-prompt-evaluation/images/ai-guardrails.png)

3. Save the prompt.

## watsonx Challenge<a name="4"></a>
Some have run into cloud issues because of the instance that was created during the watsonx Challenge back in August.

![watsonx-challenge](./lab1-assisted-prompt-evaluation/images/watsonx-challenge.png)

If your team created a separate cloud instance for the watsonx challenge, go ahead and delete the instance, then reload the projects page.
