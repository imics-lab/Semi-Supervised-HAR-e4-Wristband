These are alternate labels that replace the originals in the TWristAR dataset.
Lee B. Hinkle May 24, 2022

The original dataset is correct but only has three subjects.  And the associated
demo code performs hold-one-subject out for each of the subjects.

However, for the paper we wanted to put only and exclusively Subject 3's data
into the test set.

With only two subjects left for training and validation it would be difficult
to train on only one and validate on the other.   So the workaround is to create
two fake subjects 11 and 21 which have a select number of the individual activities
loaded.  This way the underlying code does not have to be changed.

Here is the original 1574622389_A01F11_labels.csv in the dataset on Zenodo.
start,finish,label,sub
2019:11:24 19:07:31,2019:11:24 19:08:32,Jogging,1
2019:11:24 19:08:32,2019:11:24 19:09:31,Walking,1
2019:11:24 19:09:31,2019:11:24 19:10:31,Jogging,1
2019:11:24 19:10:31,2019:11:24 19:11:31,Walking,1
2019:11:24 19:11:31,2019:11:24 19:12:31,Jogging,1
2019:11:24 19:12:31,2019:11:24 19:13:33,Walking,1

and here is the alternate version in this directory
start,finish,label,sub
2019:11:24 19:07:31,2019:11:24 19:08:32,Jogging,1
2019:11:24 19:08:32,2019:11:24 19:09:31,Walking,1
2019:11:24 19:09:31,2019:11:24 19:10:31,Jogging,11
2019:11:24 19:10:31,2019:11:24 19:11:31,Walking,11
2019:11:24 19:11:31,2019:11:24 19:12:31,Jogging,1
2019:11:24 19:12:31,2019:11:24 19:13:33,Walking,1

So the middle Jogging and Walking segments will be placed in the validation
group when the code is called such that Subject 11 is in validation.

To recap, since there are only two subjects left after keep Sub3 in Test
Sub1 and Sub2 have a few of their individual activities marked as 11 and 21
respectively.  The data associated with "fake" sub 11 and 21 will be 
placed into the validation set.
