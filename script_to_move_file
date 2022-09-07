#need to put this script with files in the same folder.

#Files containing this keyword will be moved
filekey="CARM"
files=`ls -l|grep -v ^d|awk '{print $NF}'|grep $filekey`
echo `date` "|INFO| Files ready to move about: "$files >> log
for file in ${files[@]}
do
    folderkey=`echo $file|awk -F '_' '{print $NF}'|awk -F '.' '{print $1}'`
    if [[ ! -d $folderkey ]];then
        mkdir $folderkey
    fi
    mv $file $folderkey
    if [[ $? -ne 0 ]];then
        echo `date` "|ERROR| Move $file to $folderkey FAIL" >> log
    else
        echo `date` "|INFO| Move $file to $folderkey SUCCESS" >> log
    fi
done
