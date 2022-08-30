# Audio Assessment
Assessing comfort level of an audio by ConvNet. 

## Training

### In `Create_dataset.ipynb`
Datasets are the audio files from linebot, total 11822 records.\
After eliminating datas that difference between `Feel_score` and `Feel_health` is more than two, remain 11113 records.\
Then, make the dataset to be balanced as far as possible. Only remain 3823 records.\
Extract STFT(Short Time Fourier Transfer) as features. Split dataset to training and testing for 80% and 20%.
Then dump datasets using `pickle.dump()`.

### In `Audio_Assessing.ipynb`
Model is trained by ConvNet.

## Results
There are two kinds of prediction.
1. Only categorized into uncomfortable(1, 2, 3) and comfortable(4, 5) two classes. Test accuracy=0.7 .
2. Keep the prediction as a number between 1~5, test mean absolute error=0.86 .

## Summary
After a lot of trying, the poor performance might be caused by:
1. The training audio is recorded by phone, so it contains a lot of noises.
2. The ConvNet design is not complicated enough.