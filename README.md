# Jarvix-QA
We label about 300 Jarvix questions for label as following:
'''
{"O":0, "I-Column": 1, "B-Column":2, "I-Operation":3, "B-Operation":4, "I-Restriction":5, "B-Restriction":6, "I-Pattern":7, "B-Pattern":8, "I-Others":9, "B-Others": 10}
'''

Using mLuke to fine-tune the ner tag with command:

'''
export TASK_NAME=ner

python fine_tune_mluke.py --validation_file data/valid.json  --model_name_or_path studio-ousia/mluke-base --train_file data/train.json   --task_name $TASK_NAME   --max_length 128   --per_device_train_batch_size 32   --learning_rate 2e-5   --num_train_epochs 3   --output_dir /tmp/$TASK_NAME/
'''