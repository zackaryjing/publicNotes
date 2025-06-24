 # DataTypes
 VBO (Vertex buffer object) stores vertices in GPU's memory.

```cpp
glGenBuffers(...,<ID>) // Create buffer id
glBindBuffer(<type of data>,<ID>) // bind buffer allocating space?
glBufferData(<type of data>,<size>,<data(struct)>,<mods>) // copy data to the actual buffer
// mods:
// GL_STREAM_DRAW: the data is set only once and used by the GPU at most a few times.  
// GL_STATIC_DRAW: the data is set only once and used many times.  
// GL_DYNAMIC_DRAW: the data is changed a lot and used many times.
```

VAO (Vertex array object) VAO Stores VBO 

```cpp
// vertex attributes pointers  
glVertexAttribPointer(0, 3, GL_FLOAT,GL_FALSE, 3 * sizeof(float), reinterpret_cast<void *>(0));  // second param is 3 because we are using vec3
  
// vertex attribute location  
glEnableVertexAttribArray(0);
```

```cpp
// create and bind vertex array object  
unsigned int VAO;  
glGenVertexArrays(1, &VAO);  // first argument is the size of second argument
							// we can use array<GLuint,size> in cpp
							// bind multiple arrays at once
glBindVertexArray(VAO);  
  
  
// create vertex buffer object  
unsigned int VBO;  
glGenBuffers(1, &VBO);  // similar to VAO bind.
glBindBuffer(GL_ARRAY_BUFFER, VBO);
```

EBO (Element buffer object)

About how to draw a polygon: 
```cpp
glPolygonMode(GL_FRONT_AND_BACK,GL_LINE);  // set 
glPolygonMode(GL_FRONT_AND_BACK,GL_FILL);  // unset
```

# GSQL
A vector in GLSL is a 1,2,3 or 4 component container for any of the basic types just mentioned.  
They can take the following form (n represents the number of components):  
•vecn: the default vector of n floats.  
•bvecn: a vector of n booleans.  
•ivecn: a vector of n integers.  
•uvecn: a vector of n unsigned integers.  
•dvecn: a vector of n double components

When vertex shader output variable has the same name and type with the fragment shader , they would be connected.


