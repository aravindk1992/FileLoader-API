# FileLoader-API

The following is a file Loader script that tweaks the existing sklearn.datasets load_files function to recursively load nested directory structure.
The Following script expects you to have installed sklearn. If not already installed do a : pip install sklearn or sudo pip install sklearn
Load text files with categories as subfolder names. Individual samples are assumed to be files stored a heirarchical folder structure such as the following:
    container_folder/
        Intermediate_folder1/......
            category_1_folder/
                file_1.txt
                file_2.txt
                ...
                file_42.txt
        Intermediate_folder1/......
            category_2_folder/
                file_43.txt
                file_44.txt
            ...
The folder names are used as supervised signal label names. The
individual file names are not important.
This function does not try to extract features into a numpy array or
scipy sparse matrix. In addition, if load_content is false it
does not try to load the files in memory.
To use text files in a scikit-learn classification or clustering
algorithm, you will need to use the `sklearn.feature_extraction.text`
module to build a feature extraction transformer that suits your
problem.
If you set load_content=True, you should also specify the encoding of
the text using the 'encoding' parameter. For many modern text files,
'utf-8' will be the correct encoding. If you leave encoding equal to None,
then the content will be made of bytes instead of Unicode, and you will
not be able to use most functions in `sklearn.feature_extraction.text`.
Similar feature extractors should be built for other kind of unstructured
data input such as images, audio, video, ...
