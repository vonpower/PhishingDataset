

#how to use:
import dill
dill_file="vonDataset20180426.dill"
with open(dill_file, 'rb') as f:
        pickleData=dill.load( f )
        train_x,train_y=pickleData["train_x"],pickleData["train_y"]
        val_x,val_y=pickleData["val_x"],pickleData["val_y"]
        test_x,test_y=pickleData["test_x"],pickleData["test_y"]
        char_to_int=pickleData["char_to_int"]
print("\t\t\tFeature Shapes:")
print("Train set: \t\t{}".format(train_x.shape), 
      "\nValidation set: \t{}".format(val_x.shape),
      "\nTest set: \t\t{}".format(test_x.shape))