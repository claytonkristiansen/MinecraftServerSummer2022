<h1 id="lmk3hxxxx-uvm-environment-documentation">LMK3HXXXX UVM Environment Documentation</h1>

Any items not present in this documentation may be present in the [UVM 1.1 Documentation](https://www.accellera.org/images/downloads/standards/uvm/UVM_1.1_Class_Reference_Final_06062011.pdf)  

Table of Contents:

- [Modules:](#modules)
- [Classes:](#classes)
  - [my_report_server](#my_report_server)
  - [base_test](#base_test)
    - [base_test::new](#base_testnew)
    - [base_test::build_phase](#base_testbuild_phase)
    - [base_test::connect_phase](#base_testconnect_phase)
    - [base_test::end_of_elaboration_phase](#base_testend_of_elaboration_phase)
    - [base_test::reset_phase](#base_testreset_phase)
    - [base_test::main_phase](#base_testmain_phase)
    - [base_test::pre_configure_phase](#base_testpre_configure_phase)
    - [base_test::shutdown_phase](#base_testshutdown_phase)
    - [base_test::report_phase](#base_testreport_phase)
    - [base_test::readf](#base_testreadf)



# Modules:




# Classes:

## my_report_server
```sv
class my_report_server extends uvm_report_server;
```
Description to come



## base_test
```sv
class base_test extends uvm_test;
```
The parent testcase class. This class contains many objects, functions, and tasks that are necessary to create a testcase. All testcase classes must extend base_test.

<!-- ### Functions/Tasks: -->

### base_test::new
Method of [base_test](#base_test)
```sv
function new (string name = "base_test", uvm_component parent, time TIMEOUT = `MAX_TIMEOUT);
```
Constructor for the base_test class.

-------------------------------------------

### base_test::build_phase
Method of [base_test](#base_test)
```sv
virtual function void build_phase (uvm_phase phase);
```
base_test implementation of the UVM phase where the testbench components are constructed and configured. All three of the build_phase, connect_phase, and end_of_elaboration_phase functions are considered part of the overall "build phase".

-------------------------------------------

### base_test::connect_phase
Method of [base_test](#base_test)
```sv
virtual function void connect_phase (uvm_phase phase);
```
base_test implementation of the UVM phase where the TLM ports of the components are connected.

-------------------------------------------

### base_test::end_of_elaboration_phase
Method of [base_test](#base_test)
```sv
virtual function void end_of_elaboration_phase (uvm_phase phase);
```
base_test implementation of the UVM phase used to make any final adjustments to the structure, configuration or connectivity of the testbench before simulation starts. 

-------------------------------------------

### base_test::reset_phase
Method of [base_test](#base_test)
```sv
virtual task reset_phase (uvm_phase phase);
```
See [Verification Guide: Build Phases](https://verificationguide.com/uvm/uvm-phases) for information on this task being overriden.

-------------------------------------------

### base_test::main_phase
Method of [base_test](#base_test)
```sv
virtual function void main_phase (uvm_phase phase);
```
See [Verification Guide: Build Phases](https://verificationguide.com/uvm/uvm-phases) for information on this function being overriden.

-------------------------------------------

### base_test::pre_configure_phase
Method of [base_test](#base_test)
```sv
virtual function void pre_configure_phase (uvm_phase phase);
```
See [Verification Guide: Build Phases](https://verificationguide.com/uvm/uvm-phases) for information on this function being overriden.

-------------------------------------------

### base_test::shutdown_phase
Method of [base_test](#base_test)
```sv
virtual function void shutdown_phase (uvm_phase phase);
```
See [Verification Guide: Build Phases](https://verificationguide.com/uvm/uvm-phases) for information on this function being overriden.

-------------------------------------------

### base_test::report_phase
Method of [base_test](#base_test)
```sv
virtual function void report_phase (uvm_phase phase);
```
See [Verification Guide: Build Phases](https://verificationguide.com/uvm/uvm-phases) for information on this function being overriden.

-------------------------------------------

### base_test::readf
Method of [base_test](#base_test)
```sv
virtual task readf (string field, output logic [DATA_WIDTH-1:0] value, input logic [DATA_WIDTH-1 : 0] edata = 'x);
```
Reads data from a register field.

The default value of expected data will be 'x. If we didn't give any expected value to check against, then the task will check it against the value in the environment

Inputs : Field name, expected data(optional)

Output : Read value of the field

-------------------------------------------
