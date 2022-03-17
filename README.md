## NVCC Plugin for Jupyter notebook

Provides three magic cells with different capabilities. 

### Usage

- Load Extension
> `%load_ext nvcc_plugin`

- To compile and run a CUDA cell
> `%%cu`
> and add your code below

- To compile with specific flags and run a CUDA cell
> `%%cuf -f-flag1+-flag2`
>> WHERE: all the required nvcc flags are concatenated with interleaved character `+` 
>> (do not leave any blank space nor among flags neither after `-f`)

- Mark a cell to be treated as cuda library
> `%%cuda --name example.cu --compile false`
>> NOTE: The cell must contain either code or comments to be run successfully. 
>> It accepts 2 arguments. `-n` | `--name`  - which is the name of either CUDA source or Header
>> The name parameter must have extension `.cu` or `.h`
>> Second argument `-c` | `--compile`; default value is `false`. The argument is a flag to specify
>> if the cell will be compiled and run right away or not. It might be useful if you're playing in
>> the `main` function
