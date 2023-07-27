# Resource Manager

### Introduction 

The SuperAGI Resource Manager facilitates the structured storage and retrieval of files generated by autonomous agents. This component ensures smooth operations of agents, allowing them to read from and save to designated directories based on their unique identification and execution parameters.

### **Configuration**

### Local Configuration

For local setups, the configuration is specified through the **`config.yaml`** file. In this file, paths are set using the following parameters:

- **`RESOURCES_INPUT_ROOT_DIR`**: Designates the root directory for agent inputs. It follows the pattern: **`workspace/input/{agent_id}`**.
- **`RESOURCES_OUTPUT_ROOT_DIR`**: Specifies the root directory where agent outputs are saved. Two configurations are available:
    - Per Execution: **`workspace/output/{agent_id}/{agent_execution_id}`**
    - Per Agent: **`workspace/output/{agent_id}`**

### Production (Cloud Version) Configuration

In the cloud or production environment, input and output directories configurations are preset and cannot be changed.

### **Working Mechanism**

### Concurrent Agent Operation

The SuperAGI infrastructure supports seamless concurrent operations of multiple agents. Each agent, distinguished by its unique **`agent_id`**, can run without interference from others.

### File Storage and Retrieval

When an agent generates a file during its execution:

1. The file is saved to its corresponding output directory.
2. If configured at the execution level, the file will reside under the specific **`agent_execution_id`** directory.
3. Otherwise, it will be stored at the agent level directory.

For reading files, agents access their designated input directory.

### **User Interface (UI) Representation**

In the user interface:

- **Outputs**: Users can view files on a per-execution basis. Each execution's stored files are displayed distinctly, allowing users to track and manage the outputs for each run of an agent.
- **Inputs**: Files are displayed on an agent-wise basis, ensuring clarity in tracking resources used for agent operations.

### 

[![Resource Manager](/../assets/images/Resource_manager.png)](/../assets/videos/resource_manager.mp4)