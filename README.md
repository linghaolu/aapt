# aapt
fix android aapt bugs

1. bugs of "aapt add":     
   Use aapt add a file to the zip, the new zip entry's last modify time is not correct.
   
2. bugs of "aapt remove":     
   Delete the first zip entry in the apk file will cause failure.     
   It only delete the entry from the Central Directory area, but not deleted from the Local File Header.    
   
3. bugs of "aapt remove":    
   If the central directory entries' index sequence not as the same of the Local File Header entries' index.  delete operation will cause a problem.    
   (Use Android gradle plugin 2.2 to build the debug-type apk will generate a zip file described above, The central directory entries not
   sorted by LFH offset)    
   
   
