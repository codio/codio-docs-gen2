.. meta::
   :description: Student Submission Options
  
.. _student-submission:

Student submission options
==========================
There are two important settings that control

- the way that a student submits individual questions and
- the way a student notifies the course instructors that a assignment is completed.

The submit button
-----------------
Until November 20th 2017, each assessment has a submit button beneath the assessment. Once pressed, the answer is autograded, if an MCQ, Fill In The Blank or Free Text question. If the **One attempt only** setting is selected for the assessment, then the student will be warned that they will not be able to resubmit. If this setting is not selected, then they will be able to resubmit a response.

It is now possible to suppress the submit button entirely. The advantage of this is that students do not need to worry about the effect of pressing the button. They can simply provide a response and then move on to other assessments or pages in the guide.

To suppress the use of the **Submit** button, you should go to the global settings tab in the guide and disable **Use submit buttons**.

  .. image:: /img/guides/globalsettings.png
     :alt: Global Settings


Once the project is marked as complete (see below) then all assessment responses are fully submitted automatically. You should make sure that all students' work is marked as complete either manually or using the automated mark as complete option on the final deadline.

Mark as Complete
----------------
To suppress the student **Mark as complete** action, you should go to the guide global settings (see above screenshot) and disable **Use mark as complete**.

A student can proactively mark as assignment as complete. This can trigger an :ref:`assignment level autograde script <auto-grade-scripts>` and it is also flagged up in the teacher dashboard against that student.

The drawback to using the student driven mark as complete option is that once students mark a assignment as complete, they are no longer able to make changes to the assignment, including answering assessments. The advantage is that instructors are able to grade those students' work ahead of a deadline.

If the project has been marked as completed, students can click on the 'completed' button to access the grade feedback but if they wish to view the project, direct them to click on the name of the project on the left hand side. As the assignment is completed they will not be able to edit anything but can view the content.

It is possible to disable the student side mark as complete option entirely so students do not need to think about doing it. It also means that instructors don't get requests from students to re-enable the assignment if they submitted by mistake or decided they want to change something.

If you do not want students to mark as complete, then you will likely want to do one of the following

- Once an arbitrary deadline has been reached, after which you want to start grading student work, you should :ref:`mark all students' work as complete <grading>` from the assignment actions area.
- Set an :ref:`end of assignment date <assignment-duration>` and specify that once the date is reached, the students' work should be marked as complete automatically.



Penalty deadlines
-----------------
Another powerful feature that you may want to use is **Penalty deadlines**. This allows you to specify deadlines, before the final grading deadline, where a percentage deduction of the final grade is made. :ref:`Click here <penalties>` for more information on managing penalty deadlines.