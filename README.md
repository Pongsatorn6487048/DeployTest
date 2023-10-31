## T3: 'testGetHighStars()'

### วัตถุประสงค์
จุดประสงค์ของ test case คือ สร้างขึ้นมาเพื่อตรวจสอบว่า function `getHighStar` คืนค่า HighStars  ถูกต้องตรงกับ expected result

### Interface-Base

* Develop characteristics
  * C1 = Theme id is correct
  * C2 = Difficulty value is correct

* Partition characteristics

  | Characteristic                              | b1  | b2 |
  |--------------------------------------------|----|----|
  | C1: Theme id is correct     | True  | False  |
  | C2: Difficulty value is correct | True  | False  |

* Identify (possible) values

  | Characteristic                              | b1  | b2 |
  |--------------------------------------------|------------------------|---------------------------|
  | C1: Theme id is correct          | 1  | -1  |
  | C2: Difficulty value is correct  | 1  | -1  |

### Functionality-Base

* Develop characteristics
  * C1 = สามารถสร้าง key ที่ได้มาจาก Theme และ Difficulty เพื่อหาค่าใน SharedPreferences

* Partition characteristics

  | Characteristic                                | b1  | b2 |
  |----------------------------------------------|----|----|
  | C1: สามารถสร้าง key ที่ได้มาจาก Theme และ Difficulty เพื่อหาค่าใน SharedPreferences              | True  | False  |
  
* Identify (possible) values

  | Characteristic                                | b1  | b2 |
  |----------------------------------------------|------------------------|---------------------------|
  | C1: สามารถสร้าง key ที่ได้มาจาก Theme และ Difficulty เพื่อหาค่าใน SharedPreferences               |  (1, 1)  |  (-1, 0)  |

### Input domain modelling
1. Identify testable functions 
   * getHighStars()
2. Identify parameters, return types, return values, and exceptional behavior	
   * Parameters: theme, difficulty
   * Return type: int
   * Return value: ค่าที่ได้จาก SharedPreferences ถ้าหากไม่พบค่าใน SharedPreferences จะคืนค่า-1
   * Exceptional behavior: ??
3. Model the input domain
   * Develop characteristics 
     * C1 = Theme id is correct
     * C2 = Difficulty value is correct
   * Partition characteristics
   
     | Characteristic                                | b1  | b2 |
     |----------------------------------------------|----|----|
     | C1: Theme id is correct                | True  | False  |
     | C2: Difficulty value is correct         | True  | False  |

   * Identify (possible) values

     | Characteristic                                | b1  | b2 |
     |----------------------------------------------|------------------------|---------------------------|
     | C1: Theme id is correct              | 1 | -1  |
     | C2: Difficulty value is correct         | 1  | -1  |

4. Combine partitions into tests
   * Assumption: choose Each Choice Combination (ECC) 
   * Test requirements -- number of tests (lower bound) = 2
   * C1:C2 -> (C1b1, C2b1) , (C2b1, C2b2)
5. Derive test values
   
     |   Test  | Theme  |  Difficulty | Expected result |
     |----- | :-------------: | :-------------: | :-------------: |
     |T1(True, True) | 1 | 1  | 5  |
     |T2(True, False) | -1 | -1  | -1  |
     



## T10: 'testgetBestTimeForStage()'

### วัตถุประสงค์
จุดประสงค์ของ test case คือ สร้างขึ้นมาเพื่อตรวจสอบว่า bestTime มีข้อมูลที่เก็บไว้อยู่หรือเปล่า ถ้ามีจะถูกแปลงหน่วยให้เป็น minutes, seconds และ คืนค่ากลับในรูปแบบ String 

### Interface-Base

* Develop characteristics
  * C1 = Theme id is correct
  * C2 = Difficulty value is correct
  * C3 = bestTime value is correct

* Partition characteristics

  | Characteristic                              | b1  | b2 |
  |--------------------------------------------|----|----|
  | C1: Theme id is correct      | True  | False  |
  | C2: Difficulty value is correct  | True  | False   |
  | C3: bestTime value is correct  | True | False  |

* Identify (possible) values

  | Characteristic                              | b1  | b2 |
  |--------------------------------------------|----|----|
  | C1: Theme id is correct     | 1  | -1  |
  | C2: Difficulty value is correct  | 1  | -1  |
  | C3: bestTime value is correct  | 1  | -1  |

### Functionality-Base

* Develop characteristics
  * C1 = สามารถดึงข้อมูลที่ได้มาจาก theme และ difficulty เพื่อหาค่าใน Memory

* Partition characteristics

  | Characteristic                                | b1  | b2 |
     |----------------------------------------------|----|----|
     | C1: สามารถสร้าง key ที่ได้มาจาก Theme และ Difficulty เพื่อหาค่าใน SharedPreferences | True  | False  |

  
* Identify (possible) values

  | Characteristic                                | b1  | b2 |
     |----------------------------------------------|----|----|
     | C1: สามารถสร้าง key ที่ได้มาจาก Theme และ Difficulty เพื่อหาค่าใน SharedPreferences           | (1,1)  | (-1,0)  |


### Input domain modelling
1. Identify testable functions 
   * getBestTimeForStage()
2. Identify parameters, return types, return values, and exceptional behavior	
   * Parameters: theme, difficulty
   * Return type: String
   * Return value: ค่า bestTime ที่ถูกแปลงแล้ว
   * Exceptional behavior: ??
3. Model the input domain
   * Develop characteristics 
     * C1 = Theme id is correct
     * C2 = Difficulty value is correct
     * C3 = bestTime value is correct
     * C4 = สามารถสร้าง key ที่ได้มาจาก Theme และ Difficulty เพื่อหาค่าใน SharedPreferences

* Partition characteristics

  | Characteristic                              | b1  | b2 |
  |--------------------------------------------|----|----|
  | C1: Theme id is correct      | True  | False  |
  | C2: Difficulty value is correct  | True  | False   |
  | C3: bestTime value is correct  | True | False  |
  | C4: สามารถสร้าง key ที่ได้มาจาก Theme และ Difficulty เพื่อหาค่าใน SharedPreferences | True  | False  |

* Identify (possible) values

  | Characteristic                              | b1  | b2 |
  |--------------------------------------------|----|----|
  | C1: Theme id is correct     | 1  | -1  |
  | C2: Difficulty value is correct  | 1  | -1  |
  | C3: bestTime value is correct  | 1  | -1  |
  | C4: สามารถสร้าง key ที่ได้มาจาก Theme และ Difficulty เพื่อหาค่าใน SharedPreferences | (1,1)  | (-1,0)  |

4. Combine partitions into tests
   * Assumption: choose Each Choice Combinations (ECC) 
   * Test requirements -- number of tests = 2
   * C1:C2:C3:C4 -> (C1b1, C2b1, C3b1, C4b1) , (C1b2, C2b2, C3b2, C4b2)
5. Derive test values
   
   |   Test  | Theme  | Difficulty | BestTime | Theme & Difficulty can create keys |  Expected result |
     |----- | :-------------: | :-------------: | :-------------: | :-------------: | :-------------: |
     |T1 | 1 | 1  | 125   | True   | BEST : 02:05   |
     |T2 | -1 | -1  | -125  | False   | BEST : -  |



## T4: 'testSaveTime()'

### วัตถุประสงค์
จุดประสงค์ของ test case คือ สร้างขึ้นมาเพื่อตรวจสอบว่า passedSecs ที่ได้รับมาเท่ากับ bestTime ที่เก็บไว้อยู่หรือเปล่าถ้า passedSecs น้อยกว่า bestTime ค่า passedSecs จะถูกบันทึกเป็น bestTime อันใหม่

### Interface-Base

* Develop characteristics
  * C1 = Value of theme
  * C2 = Value of difficulty
  * C3 = Value of PassedSecs

* Partition characteristics

  | Characteristic                              | b1  | b2 | b3 |
  |--------------------------------------------|----|----|----|
  | C1: Value of theme      | Less than 1  | Equal to 1  | Greater than 1 |
  | C2: Value of difficulty  | Less than 1  | Equal to 1  | Greater than 1 |
  | C3: Value of PassedSecs  | Less than bestTime  | Equal to bestTime  | Greater than bestTime |

* Identify (possible) values

  | Characteristic                              | b1  | b2 | b3 |
  |--------------------------------------------|----|----|----|
  | C1: Value of theme      | 0  | 1  | 2 |
  | C2: Value of difficulty  | 0  | 1  | 2 |
  | C3: Value of PassedSecs  | 30  | 40  | 50 |

### Functionality-Base

* Develop characteristics
  * C1 = สร้าง key จาก theme และ difficulty ได้
  * C2 = ค่า PassedSecs ถูกบันทึกใหม่ที่ SharedPreferences

* Partition characteristics

  | Characteristic                                | b1  | b2 |
     |----------------------------------------------|----|----|
     | C1: สร้าง key จาก theme และ difficulty ได้              | True  | False  |
     | C2: ค่า PassedSecs ถูกบันทึกใหม่ที่ SharedPreferences         | True  | False  |
  
* Identify (possible) values

  | Characteristic                                | b1  | b2 |
     |----------------------------------------------|----|----|
     | C1: สร้าง key จาก theme และ difficulty ได้              | (1, 2)  | (-1, 0)  |
     | C2: ค่า PassedSecs ถูกบันทึกใหม่ที่ SharedPreferences         | 30  | 50  |

### Input domain modelling
1. Identify testable functions 
   * saveTime()
2. Identify parameters, return types, return values, and exceptional behavior	
   * Parameters: theme, difficulty, passedSecs
   * Return type: ไม่มีการคืนค่า (void)
   * Return value: ไม่มีการคืนค่า (void)
   * Exceptional behavior: ??
3. Model the input domain
   * Develop characteristics 
     * C1 = สร้าง key จาก theme และ difficulty ได้
     * C2 = ค่า PassedSecs ถูกบันทึกใหม่ที่ SharedPreferences

   * Partition characteristics

      | Characteristic                                | b1  | b2 | b3 |
     |----------------------------------------------|----|----|----
     | C1: Value of theme      | Less than 1  | Equal to 1  | Greater than 1 |
     | C2: Value of difficulty  | Less than 1  | Equal to 1  | Greater than 1 |
     | C3: Value of PassedSecs  | Less than bestTime  | Equal to bestTime  | Greater than bestTime |
     | C4: สร้าง key จาก theme และ difficulty ได้  | True  | False  |
     | C5: ค่า PassedSecs ถูกบันทึกใหม่ที่ SharedPreferences  | True  | False  |

   * Identify (possible) values

      | Characteristic                                | b1  | b2 | b3 |
     |----------------------------------------------|----|----|----|
     | C1: Value of theme      | 0 | 1  | 2 |
     | C2: Value of difficulty  | 0  | 1  | 2 |
     | C3: Value of PassedSecs  | 30  | 40  | 50 |
     | C4: สร้าง key จาก theme และ difficulty ได้              | (1, 2)  | (-1, 0)  |  |
     | C5: ค่า PassedSecs ถูกบันทึกใหม่ที่ SharedPreferences         | 30  | 50  |  |

5. Combine partitions into tests
   * Assumption: choose Each Choice Coverage (ECC) 
   * Test requirements -- number of tests  = 3
   * C1:C2 -> (C1B1, C2B1, C3B1, C4B1, C5B1) , (C1B2, C2B2, C3B2, C4B2, C5B2), (C1B3, C2B3, C3B3, C4B1, C5B1)
6. Derive test values
   
   |   Test  | Theme | Difficulty | PassedSecs | Theme & Difficulty can create keys | PassedSecs can Save to Shared Preferences |Expected result |
     |----- | :-------------: | :-------------: | :-------------: | :-------------: | :-------------: | :-------------: |
     |T1 | 0 | 0 | 30  | True | True | 30  |
     |T2 | 1 | 1 | 50  | False | False | Invalid Test  |
     |T3 | 2 | 2 | 50  |  True    |  True     |  40   |

* T2 = Invalid Test เพราะว่าค่า Theme & Difficulty ถูกทั้งคู่ต้องสามารถสร้าง key ได้
