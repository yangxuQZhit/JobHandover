# AbstractSingleView类

> SingleView父类

**类图**

![AbstractSingleView类图](../res/AbstractSingleView类图.png)

## 代码解析

#### 初始化

```c++
void AbstractSingleView::init() {
    generateVertices(vertices, NUM_DEVISIONS);
    generateIndices(indices, NUM_DEVISIONS);
    glGenBuffers(1, &VBO);
    glBindBuffer(GL_ARRAY_BUFFER, VBO);
    glBufferData(GL_ARRAY_BUFFER, vertices.size() * sizeof(float), &vertices[0], GL_STATIC_DRAW);
    //create the ibo for vertices
    glGenBuffers(1, &EBO);
    glBindBuffer(GL_ELEMENT_ARRAY_BUFFER, EBO);
    glBufferData(GL_ELEMENT_ARRAY_BUFFER, indices.size() * sizeof(GLushort), &indices[0], GL_STATIC_DRAW);
    //unbind
    glBindBuffer(GL_ARRAY_BUFFER, 0);
    glBindBuffer(GL_ELEMENT_ARRAY_BUFFER, 0);
}
```

#### T7顶点数据生成

```c++
void SingleViewT7::generateVertices(std::vector<float> &vertices, int num) {
    for(int i=0; i<num; i++) {
        for(int j=0; j<num; j++) {
            vertices.push_back(-1.0f + j*2.0f/(num-1));
            vertices.push_back(1.0f - i*2.0f/(num-1));
            vertices.push_back(0.0f + j*1.0f/(num-1));
            vertices.push_back(0.0f + i*1.0f/(num-1));
        }
    }
}
```

#### T7索引数据生成

```c++
void SingleViewT7::generateIndices(std::vector<GLushort> &indices, int num) {
    for(int i=0; i<num-1; i++) {
        for(int j=0; j<num-1; j++) {
            //first triangle
            indices.push_back(i * num + j);
            indices.push_back(i * num + j + 1);
            indices.push_back((i + 1) * num + j);
            //second triangle
            indices.push_back(i * num + j + 1);
            indices.push_back((i + 1) * num + j);
            indices.push_back((i + 1) * num + j + 1);
        }
    }
}
```

#### 8953顶点数据生成

```c++
void SingleView8953::generateVertices(std::vector<float> &vertices, int num) {
    for (int index = 0; index < SPLIT_IMAGE_NUM; index++) {
        for(int i=0; i<num; i++) {
            for(int j=0; j<num; j++) {
                vertices.push_back(-1.0f + j*2.0f/(num-1));
                vertices.push_back(1.0f - i*2.0f/(num-1));

                switch (index) {
                    case 0:
                        vertices.push_back(0.0f + j*0.25f/(num-1));
                        vertices.push_back(0.0f + i*1.0f/(num-1));
                        break;
                    case 1:
                        vertices.push_back(0.25f+ j*0.25f/(num-1));
                        vertices.push_back(0.0f + i*1.0f/(num-1));
                        break;
                    case 2:
                        vertices.push_back(0.5f + j*0.25f/(num-1));
                        vertices.push_back(0.0f + i*1.0f/(num-1));
                        break;
                    case 3:
                        vertices.push_back(0.75f+ j*0.25f/(num-1));
                        vertices.push_back(0.0f + i*1.0f/(num-1));
                        break;
                    default:
                        break;
                }
            }
        }
    }
}
```

#### 8953索引数据生成

```c++
void SingleView8953::generateIndices(std::vector<GLushort> &indices, int num) {
    for(int i=0; i<num-1; i++) {
        for(int j=0; j<num-1; j++) {
            //first triangle
            indices.push_back(i * num + j);
            indices.push_back(i * num + j + 1);
            indices.push_back((i + 1) * num + j);
            //second triangle
            indices.push_back(i * num + j + 1);
            indices.push_back((i + 1) * num + j);
            indices.push_back((i + 1) * num + j + 1);
        }
    }
}
```

