# Digital-electronics-1

## Laboratoře (Gates)
### 1.
Odkaz na můj [GitHub](https://github.com/xkrych01/Digital-electronics-1)

### 2.
**Zdrojový kód**

```
entity gates is
	port
    (
    	a_i : in std_logic;
        b_i : in std_logic;
        c_i : in std_logic;
        f_i : out std_logic;
        fnand_i : out std_logic;
        fnor_i : out std_logic
    );
end entity gates;


architecture dataflow of gates is 
begin 
	 f_i <= ((not b_i) and a_i) or ((not c_i) and (not b_i));
     fnand_i <= not ((not ((not b_i) and a_i)) and (not((not c_i) and (not b_i))));
     fnor_i <= not (b_i or (not a_i)) or (not (c_i or b_i));
     
end architecture dataflow;

```


**Screenshot simulace De-Morganových zákonů a upravené vzorce**
![Simulace](Images/Funkce_DeMorganovych_pravidel.jpg)
![Vzorce](Images/Vzorce.png)

**Tabulka zjištěných hodnot ze simulace**
| **c** | **b** |**a** | **f(c,b,a)** |
| :-: | :-: | :-: | :-: |
| 0 | 0 | 0 | 1 |
| 0 | 0 | 1 | 1 |
| 0 | 1 | 0 | 0 |
| 0 | 1 | 1 | 0 |
| 1 | 0 | 0 | 0 |
| 1 | 0 | 1 | 1 |
| 1 | 1 | 0 | 0 |
| 1 | 1 | 1 | 0 |




**Odkaz na EDA Playground**

[Zde](https://www.edaplayground.com/x/FiDd) najdete naprogramovanou simulaci.


### 3.


**Zdrojový kód**

```
entity gates is
	port
    (
    	x_i : in std_logic;
        y_i : in std_logic;
        z_i : in std_logic;
        f1_leva : out std_logic;
        f1_prava : out std_logic;
        f2_leva : out std_logic;
        f2_prava : out std_logic
    );

end entity gates;


architecture dataflow of gates is 
begin 
	 f1_leva <= (x_i and y_i) or (x_i and z_i);
     f1_prava <= x_i and (y_i or z_i);
     f2_leva <= (x_i or y_i) and (x_i or z_i);
     f2_prava <= x_i or (y_i and z_i);
     
end architecture dataflow;
```


**Screenshot simulace Distribučních funkcí a jejich vzorce**
![Simulace](Images/Distribucni_funkce.jpg)
![Vzorce](Images/Distribucni_fce.png)


**Odkaz na EDA Playground**

[Zde](https://www.edaplayground.com/x/8NYQ) najdete naprogramovanou simulaci.
