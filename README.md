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
