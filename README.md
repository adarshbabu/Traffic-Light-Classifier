# Traffic-Light-Classifier
Accuracy - 97% 

*features*
- Average brighntess extraction
- Masking feature - return- Masked+Cropped


**Masking**
```
    if avg_brightness>170:                          ex: range 170 to 180
        s=s+50                                      #increase saturation for bright foggy conditions
    if avg_brightness<200:
        mask = cv2.inRange(s,30, 285)              #saturation mask for good saturation distinct images
        masked_image = np.copy(image)
        masked_image[mask == 0] = [0, 0, 0]
    else:     
        mask = cv2.inRange(gray_image,0, 100)       #grascale mask for bright foggy images range 0 to <100        
        masked_image = np.copy(image)               
        masked_image[mask != 0] = [0, 0, 0]
```
*Need to push accuracy to 100 and shorten the code*
