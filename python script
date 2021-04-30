# To copy all files from a folder with multiple subfolders into a single folder. Even if there are repeated filenames, the later files will automatically have numbers
#appended in paranthesis to distinguish them from earlier files with the same name. Further, the program will print out the original and renamed filenames for
#files that have been renamed

import shutil
from pathlib import Path
import os

def new_path(file_name):
    fake_path = 'D:/fake'
    fake_path = Path(fake_path)
    file_name_path = fake_path/file_name
    file_name = file_name_path.stem
    file_suffix = file_name_path.suffix
    len_file = len(file_name)
    if (file_name[len_file - 1] == ')') and (file_name[len_file - 3] == '(') and file_name[len_file - 2].isnumeric():
        new_number = int(file_name[len_file - 2]) + 1
        new_name = file_name[0:len_file - 2] + str(new_number) + ')' + file_suffix
        return new_name
    else:
        new_name = file_name + '(1)' + file_suffix
        return new_name

def copy_all_new(input_path,output_path):
    y = []
    for folderName, subfolders, filenames in os.walk(input_path):
        y = y + [folderName]
    length_y = len(y)
    for i in range(0, length_y):
        p11 = Path(y[i])
        dir_path = os.listdir(p11)
        length_dir_path = len(dir_path)
        for k in range(0,length_dir_path):
            for_test = p11/dir_path[k]
            if for_test.suffix != '':
                p22 = Path(output_path)
                output_list = os.listdir(p22)
                test_name = for_test.name
                output_path_1 = output_path
                while test_name in output_list:
                    test_name = new_path(test_name)
                    if test_name in output_list:
                        continue
                    else:
                        print(for_test, 'has been copied to', p22 / test_name)
                        output_path_1 = p22 / test_name
                        break
                shutil.copy(for_test,output_path_1)


