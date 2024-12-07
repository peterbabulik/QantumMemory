# Quantum Memory Network

A Python implementation of a quantum-inspired neural network system for memory storage, retrieval, and pattern recognition using quantum computing principles.

## Overview

This project implements a hybrid quantum-classical neural network that combines quantum computing principles with traditional neural network architectures to create a sophisticated memory system. The implementation uses Cirq for quantum circuit simulation and supports various types of memory storage, retrieval, and pattern recognition.

## Key Features

- **Quantum State Encoding**: Converts classical information into quantum states
- **Multiple Memory Types**: Supports short-term, long-term, associative, and procedural memories
- **Association-based Retrieval**: Retrieves memories based on quantum similarity measures
- **Memory Consolidation**: Implements memory decay and strengthening mechanisms
- **Pattern Recognition**: Identifies and stores patterns across multiple memories
- **Interactive Testing**: Includes both automated and interactive testing interfaces

## Requirements

```python
numpy
cirq
matplotlib
```

## Architecture

### Core Components

1. **QuantumNeuralRegion**
   - Manages individual neural regions with quantum properties
   - Handles synaptic connections and quantum states
   - Implements qubit initialization and management

2. **QuantumMemoryNetwork**
   - Main class implementing the quantum memory system
   - Manages memory storage, retrieval, and consolidation
   - Handles quantum circuit creation and simulation

3. **Memory States**
   - `MemoryState`: Immutable dataclass representing quantum memory states
   - `MemoryType`: Enum defining different types of memory
   - `MemoryPattern`: Represents patterns of connected memories

## Implementation Details

### Quantum State Encoding

```python
def _encode_memory(self, content: Any) -> np.ndarray:
    """
    Encodes classical information into quantum states using:
    - Quantum circuits with rotation gates
    - Entanglement operations
    - Amplitude encoding
    """
```

### Memory Storage

```python
def store_memory(self, 
                content: Any,
                memory_type: MemoryType,
                associations: Set[str] = None) -> MemoryState:
    """
    Stores new memories with:
    - Quantum state encoding
    - Association mapping
    - Capacity management
    - Strength initialization
    """
```

### Memory Retrieval

```python
def retrieve_memory(self, 
                   query: Any,
                   memory_type: Optional[MemoryType] = None,
                   top_k: int = 5) -> List[Tuple[MemoryState, float]]:
    """
    Retrieves memories based on:
    - Quantum similarity measures
    - Memory type filtering
    - Strength-based ranking
    """
```

## Usage Examples

### Basic Usage

```python
# Initialize the network
network = QuantumMemoryNetwork(
    n_regions=2,
    neurons_per_region=3,
    synapses_per_neuron=2
)

# Store a memory
memory = network.store_memory(
    content="example content",
    memory_type=MemoryType.LONG_TERM,
    associations={"tag1", "tag2"}
)

# Retrieve similar memories
retrieved = network.retrieve_memory(
    query="example",
    memory_type=MemoryType.LONG_TERM
)
```

### Interactive Testing

```python
# Run interactive test mode
run_interactive_test()
```

## Memory Types

1. **Short Term Memory**
   - Temporary storage
   - Higher decay rate
   - Limited capacity

2. **Long Term Memory**
   - Persistent storage
   - Lower decay rate
   - Association-based strengthening

3. **Associative Memory**
   - Connection-based storage
   - Pattern recognition
   - Relationship mapping

4. **Procedural Memory**
   - Sequential information storage
   - Process-based encoding
   - Action sequence recognition

## Quantum Features

1. **Quantum Encoding**
   - Uses quantum circuits for information encoding
   - Implements quantum superposition principles
   - Utilizes quantum entanglement for relationships

2. **Quantum Similarity**
   - Based on quantum state fidelity
   - Handles superposition states
   - Quantum interference effects

3. **Quantum Circuits**
   - Rotation gates (RY, RZ)
   - Entanglement operations (CNOT)
   - Quantum state preparation

## Performance Considerations

- Memory capacity scales with quantum register size
- Retrieval time depends on number of stored memories
- Consolidation process affects memory retention
- Association network impacts retrieval accuracy

## Future Improvements

1. **Scalability**
   - Implement distributed quantum memory storage
   - Optimize quantum circuit depth
   - Add parallel processing capabilities

2. **Features**
   - Add hierarchical memory organization
   - Implement quantum error correction
   - Add more sophisticated pattern recognition

3. **Integration**
   - Add support for quantum hardware backends
   - Implement classical-quantum hybrid optimization
   - Add distributed computing capabilities

## Contributing

Contributions are welcome! Please feel free to submit pull requests.
