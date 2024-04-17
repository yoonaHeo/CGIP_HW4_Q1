# ��ǻ�ͱ׷��Ƚ��׿���ó�� ���� 1

- �� ������ ���� ȯ�����δ� vscode�� cmake�� ����Ͽ����ϴ�.
- �ʱ� ȯ�� ���� �� openGL�� �ٷ�� ���� �ʿ��� ��ų�� ��ũ�� ���󰡸� Ȯ���Ͻ� �� �ִ� [��Ʃ�� ���� ������](https://www.youtube.com/playlist?list=PLvNHCGtd4kh_cYLKMP_E-jwF3YKpDP4hf)�� �����Ͽ� �����Ͽ����ϴ�.
- OpenGL�� glm�� Ȱ���Ͽ� transformation�� �����ϴ� ����� [link](https://blog.naver.com/junsueg5737/220511107783)�� �����Ͽ����ϴ�.

---

### ���� ����
- [ȯ�� ����](#ȯ��-����)

- [���� ���](#����-���)

- [��� ȭ��](#���-ȭ��)

- [Code ����](#code-����)

---

### ȯ�� ����

- vscode version 1.87�� ����Ͽ����ϴ�.
- cmake�� �ּ��� version 3.23�� ����ؾ� �մϴ�.
- �� repository�� �ִ� CMakeLists.txt�� Dependency.cmake ������ ���� �ʿ��� library�� �ʱ� ���� �� �� ���� �ٿ�ε� ���� �� �ֽ��ϴ�.

---

### ���� ���

1. vscode�� ���� ��, �ش� project�� �ִ� directory�� ���� project folder�� load���ݴϴ�.
2. CMake�� ���� vscode extension�� �ʿ��ϹǷ�, extension�� �������� �ʴ´ٸ� vscode ������ Extensions �ǿ��� cmake�� �˻��Ͽ� CMake�� CMake Tools�� install ���ݴϴ�.
3. Windows ȯ�濡���� ctrl + shift + p, Mac ȯ�濡���� cmd + p Ű�� �Է��Ͽ� command�� �Է��� �� �ִ� â���� cmake�� �˻� �� CMake:Configure�� �����ϰ�, �ü���� �°� �����Ϸ� ŰƮ�� �����մϴ�.

    (Ȥ�� �ش� ������Ʈ�� �ִ� �������� cmd â�� ���� code .�� �Է��ϸ� �ڵ����� CMake project���� �ν��ϰ� configure�� ���� �˾��� ��ϴ�.)

    Configure�� �����ϸ� vscode �ϴ��� OUTPUT �ǿ� "Configuring project: CGIP_hw1"�̶�� ��µǴ� ���� Ȯ���Ͻ� �� �ֽ��ϴ�.

4. CMake ������Ʈ�� �ν��� �Ǿ�����, �ٽ� command�� �Է��� �� �ִ� â�� ���� CMake�� �˻��Ͽ� CMake:Build�� �����մϴ� (Ȥ�� ����Ű�� F7�� �Է��մϴ�).

    �ʱ� build���, �̶� �ʿ��� library�� ���� build ������ �ٿ�ε� �˴ϴ�.

5. �ʱ� build�� ��ģ ��, ctrl + F5�� �Է��ϸ� Debug ���� project�� ����˴ϴ�.
Debug ����̹Ƿ� �ϴ��� DEBUG CONSOLE���� ��� �� ������ Ȯ���� �� �ֽ��ϴ�.

---

### ��� ȭ��

- Q1�� ���� ��� ȭ���� ������ �����ϴ�.
    - triangle mesh�� ������ sphere�� ���Ͽ� �� ǥ�� ���� unshaded�� ���� ����� ������� ��Ÿ�� ȭ���Դϴ�.
<p align="center">
    <img src = "screenshot/Screenshot_Q1.png">
</p>

---

### Code ����

- ��� �ҽ��ڵ� ������ src ������ �ֽ��ϴ�.
    - sphere_scene.cpp ������ �⺻���� ������ ������ ������ �����Դϴ�.
    
        �Ʒ��� sphere_scene.cpp ���Ͽ��� ������ ���뿡 ���� �����Դϴ�.

- glm::vec3* vertices ����

    �� ������ ���� vertex���� ���� �����ϱ� ���� vec3 array�Դϴ�.

    �ش� ������ ���� create_scene() �Լ� ������ ������ ���� �ʱ�ȭ�˴ϴ�.
    ```
    vertices = new vec3[gNumVertices];
    ```
    for loop ������, vertices �������� ������ ���� ���� ������ �˴ϴ�.
    ```
    vertices[t] = vec3(x, y, z);
    ```
    ���� t ���� �ϳ��� �������� for loop�� ���鼭 �Ź� ���ο� vertex ���� array�� �����ϵ��� �մϴ�.

    ���������� for loop�� �������� ���� ������ ������ �����մϴ�.
    ```
    vertices[t++] = vec3(0, 1, 0);

    vertices[t++] = vec3(0, -1, 0);
    ```
    ������ t++;�� �ۼ��Ǿ� �ִ� �κ��� ���� ���� ��ü�Ͽ����ϴ�.
    
    �� �ܿ� ������ �κ��� �����ϴ�.

    - main.cpp ������ ������ �ٽ��� �Ǵ� �����Դϴ�.

        �Ʒ��� main.cpp ������ �� �Լ��� ���Ͽ� �����ϱ� ���� �����Դϴ�.

- mat4 multipl_mtx_mtx (mat4 mtx_a, mat4 mtx_b) �Լ�

    �� �Լ��� 4���� ��� ���� ���� ���Ͽ� ������ �Լ��Դϴ�.

    ��� a�� b�� �� ���Ұ��� �� �� ���� ���Ͽ� ���ο� 4���� ����� result�� �����ϰ� �̸� ��ȯ�մϴ�.

    transformation pipeline�� �����ϱ� ���Ͽ� �ʿ��� �Լ��Դϴ�.

    ```
    mat4 multipl_mtx_mtx(mat4 mtx_a, mat4 mtx_b) {
        vec4 a_row1(mtx_a[0][0], mtx_a[0][1], mtx_a[0][2], mtx_a[0][3]);
        vec4 a_row2(mtx_a[1][0], mtx_a[1][1], mtx_a[1][2], mtx_a[1][3]);
        vec4 a_row3(mtx_a[2][0], mtx_a[2][1], mtx_a[2][2], mtx_a[2][3]);
        vec4 a_row4(mtx_a[3][0], mtx_a[3][1], mtx_a[3][2], mtx_a[3][3]);

        vec4 b_row1(mtx_b[0][0], mtx_b[0][1], mtx_b[0][2], mtx_b[0][3]);
        vec4 b_row2(mtx_b[1][0], mtx_b[1][1], mtx_b[1][2], mtx_b[1][3]);
        vec4 b_row3(mtx_b[2][0], mtx_b[2][1], mtx_b[2][2], mtx_b[2][3]);
        vec4 b_row4(mtx_b[3][0], mtx_b[3][1], mtx_b[3][2], mtx_b[3][3]);

        float x11 = a_row1.x * b_row1.x + a_row1.y * b_row2.x + a_row1.z * b_row3.x + a_row1.w * b_row4.x;  //a11*b11 + a12*b21 + a13*b31 + a14*b41
        float x12 = a_row1.x * b_row1.y + a_row1.y * b_row2.y + a_row1.z * b_row3.y + a_row1.w * b_row4.y;  //a11*b12 + a12*b22 + a13*b32 + a14*b42
        float x13 = a_row1.x * b_row1.z + a_row1.y * b_row2.z + a_row1.z * b_row3.z + a_row1.w * b_row4.z;  //a11*b13 + a12*b23 + a13*b33 + a14*b43
        float x14 = a_row1.x * b_row1.w + a_row1.y * b_row2.w + a_row1.z * b_row3.w + a_row1.w * b_row4.w;  //a11*b14 + a12*b24 + a13*b34 + a14*b44

        float x21 = a_row2.x * b_row1.x + a_row2.y * b_row2.x + a_row2.z * b_row3.x + a_row2.w * b_row4.x;  //a21*b11 + a22*b21 + a23*b31 + a24*b41
        float x22 = a_row2.x * b_row1.y + a_row2.y * b_row2.y + a_row2.z * b_row3.y + a_row2.w * b_row4.y;  //a21*b12 + a22*b22 + a23*b32 + a24*b42
        float x23 = a_row2.x * b_row1.z + a_row2.y * b_row2.z + a_row2.z * b_row3.z + a_row2.w * b_row4.z;  //a21*b13 + a22*b23 + a23*b33 + a24*b43
        float x24 = a_row2.x * b_row1.w + a_row2.y * b_row2.w + a_row2.z * b_row3.w + a_row2.w * b_row4.w;  //a21*b14 + a22*b24 + a23*b34 + a24*b44

        float x31 = a_row3.x * b_row1.x + a_row3.y * b_row2.x + a_row3.z * b_row3.x + a_row3.w * b_row4.x;  //a31*b11 + a32*b21 + a33*b31 + a34*b41
        float x32 = a_row3.x * b_row1.y + a_row3.y * b_row2.y + a_row3.z * b_row3.y + a_row3.w * b_row4.y;  //a31*b12 + a32*b22 + a33*b32 + a34*b42
        float x33 = a_row3.x * b_row1.z + a_row3.y * b_row2.z + a_row3.z * b_row3.z + a_row3.w * b_row4.z;  //a31*b13 + a32*b23 + a33*b33 + a34*b43
        float x34 = a_row3.x * b_row1.w + a_row3.y * b_row2.w + a_row3.z * b_row3.w + a_row3.w * b_row4.w;  //a31*b14 + a32*b24 + a33*b34 + a34*b44

        float x41 = a_row4.x * b_row1.x + a_row4.y * b_row2.x + a_row4.z * b_row3.x + a_row4.w * b_row4.x;  //a41*b11 + a42*b21 + a43*b31 + a44*b41
        float x42 = a_row4.x * b_row1.y + a_row4.y * b_row2.y + a_row4.z * b_row3.y + a_row4.w * b_row4.y;  //a41*b12 + a42*b22 + a43*b32 + a44*b42
        float x43 = a_row4.x * b_row1.z + a_row4.y * b_row2.z + a_row4.z * b_row3.z + a_row4.w * b_row4.z;  //a41*b13 + a42*b23 + a43*b33 + a44*b43
        float x44 = a_row4.x * b_row1.w + a_row4.y * b_row2.w + a_row4.z * b_row3.w + a_row4.w * b_row4.w;  //a41*b14 + a42*b24 + a43*b34 + a44*b44

        mat4 result(vec4(x11, x12, x13, x14),
                    vec4(x21, x22, x23, x24),
                    vec4(x31, x32, x33, x34),
                    vec4(x41, x42, x43, x44));

        return result;
    }
    ```

- vec4 multipl_mtx_vec(mat4 mtx, vec4 vec) �Լ�

    �� �Լ��� 4���� ��İ� 4���� ���� ������ ���� ���� �Լ��Դϴ�.

    ��İ� ������ ���� ���� �� �� ���� ���Ͽ� ���ο� 4���� ������ result�� �����ϰ� �̸� ��ȯ�մϴ�.

    transformation pipeline�� ���� ����Ǵ� ������� ����ϱ� ���� �Լ��Դϴ�.
    ```
    vec4 multipl_mtx_vec(mat4 mtx, vec4 vec) {
        vec4 row1(mtx[0][0], mtx[0][1], mtx[0][2], mtx[0][3]);
        vec4 row2(mtx[1][0], mtx[1][1], mtx[1][2], mtx[1][3]);
        vec4 row3(mtx[2][0], mtx[2][1], mtx[2][2], mtx[2][3]);
        vec4 row4(mtx[3][0], mtx[3][1], mtx[3][2], mtx[3][3]);

        float x = row1.x * vec.x + row1.y * vec.y + row1.z * vec.z + row1.w * vec.w;    //a11*x + a12*y + a13*z + a14*w
        float y = row2.x * vec.x + row2.y * vec.y + row2.z * vec.z + row2.w * vec.w;    //a21*x + a22*y + a23*z + a24*w
        float z = row3.x * vec.x + row3.y * vec.y + row3.z * vec.z + row3.w * vec.w;    //a31*x + a32*y + a33*z + a34*w
        float w = row4.x * vec.x + row4.y * vec.y + row4.z * vec.z + row4.w * vec.w;    //a41*x + a42*y + a43*z + a44*w

        vec4 result = vec4(x, y, z, w);

        return result;
    }
    ```

- mat4 transformation_pipeline(Camera camera) �Լ�

    �� �Լ��� transformation pipeline�� �����ϱ� ���� �Լ��Դϴ�.

    ���� ������ �޾ƿ��� Camera ������ struct�� �ش��ϸ�, struct Camera�� ������ �����ϴ�.

    eye_point�� ī�޶��� ��ġ�̸�, u, v, w ���ʹ� ��ǥ �����Դϴ�.

    ���� ������ camera�� ���� ����� �����ϸ� identity matrix�� �ǹǷ�, inverse camera matrix ���� identity matrix�� �˴ϴ�.

    ```
    struct Camera {
        vec3 eye_point = vec3(0.0f, 0.0f, 0.0f);

        vec3 u = vec3(1, 0, 0);
        vec3 v = vec3(0, 1, 0);
        vec3 w = vec3(0, 0, 1);
    };
    ```

    tx, ty, tz ���� sx, sy, sz, �׸��� l, r, b, t, n, f ���� ���� ���� �ȳ� pdf�� �����ִ� �����̹Ƿ� ������ ������ �־� �ξ����ϴ�.
    
    �ʱ� ������ identity matrix�� mtx�� �ΰ� �� matrix�� ������� scaling matrix, translation matrix, camera transformation matrix, perspective projection matrix, viewport transformation matrix�� ���մϴ�.

    �׸��� ���������� mtx�� ��ȯ�ϸ�, transformation pipeline�� ��ģ ���� matrix�� ����˴ϴ�.
    ```
    mat4 transformation_pipeline(Camera camera) {
        float tx = 0.0f;
        float ty = 0.0f;
        float tz = -7.0f;

        float sx = 2.0f;
        float sy = 2.0f;
        float sz = 2.0f;
        
        float l = -0.1f;
        float r = 0.1f;
        float b = -0.1f;
        float t = 0.1f;
        float n = -0.1f;
        float f = -1000.0f;

        mat4 mtx(vec4(1, 0, 0, 0),
                vec4(0, 1, 0, 0),
                vec4(0, 0, 1, 0),
                vec4(0, 0, 0, 1));

        // translation mtx
        mat4 trans_mtx = mat4(vec4(1, 0, 0, tx),
                            vec4(0, 1, 0, ty),
                            vec4(0, 0, 1, tz),
                            vec4(0, 0, 0, 1));

        // scaling mtx
        mat4 scale_mtx(vec4(sx, 0, 0, 0),
                    vec4(0, sy, 0, 0),
                    vec4(0, 0, sz, 0),
                    vec4(0, 0, 0, 1));

        // camera transformation mtx
        mat4 camera_mtx(vec4(camera.u.x, camera.v.x, camera.w.x, camera.eye_point.x),
                        vec4(camera.u.y, camera.v.y, camera.w.y, camera.eye_point.y),
                        vec4(camera.u.z, camera.v.z, camera.w.z, camera.eye_point.z),
                        vec4(0, 0, 0, 1));

        mat4 inverse_camera_mtx = inverse(camera_mtx);
        //since camera_mtx is identity matrix, inverse_camera_mtx is also identity matrix

        // perspective projection mtx
        mat4 perspective_projection_mtx(vec4(2 * n / (r - l), 0, (l + r) / (l - r), 0),
                                        vec4(0, 2 * n / (t - b), (b + t) / (b - t), 0),
                                        vec4(0, 0, (n + f) / (n - f), 2 * f * n/ (f - n)),
                                        vec4(0, 0, 1, 0));

        // viewport transformation mtx
        mat4 viewport_trans_mtx(vec4(Nx / 2, 0, 0, (float)(Nx - 1) / 2),
                                vec4(0, Ny / 2, 0, (float)(Ny - 1) / 2),
                                vec4(0, 0, 1, 0),
                                vec4(0, 0, 0, 1));

        // transformation pipeline
        // scale -> translate -> camera -> perspective projection -> viewport transformation
        mtx = multipl_mtx_mtx(scale_mtx, mtx);

        mtx = multipl_mtx_mtx(trans_mtx, mtx);

        mtx = multipl_mtx_mtx(inverse_camera_mtx, mtx);

        mtx = multipl_mtx_mtx(perspective_projection_mtx, mtx);

        mtx = multipl_mtx_mtx(viewport_trans_mtx, mtx);

        return mtx;
    }
    ```

- main �Լ�
    
    main �Լ������� �켱 sphere_scene.cpp ������ create_scene() �Լ��� ȣ���մϴ�.
    �׸��� struct Camera ���� ȣ���մϴ�.

    ����, ��ü �̹����� ���������� �����ϴ�.
    �̹����� ���������� unsigned char image[Nx * Ny * 3]; �� ���� �����صξ����ϴ�.
    ```
    // first set image to black
    for (int i = 0; i < Nx; i++) {
        for (int j = 0; j < Ny; j++) {
            image[(j * Nx + i) * 3] = 0;
            image[(j * Nx + i) * 3 + 1] = 0;
            image[(j * Nx + i) * 3 + 2] = 0;
        }
    }
    ```

    ��������, ��ü vertex ������ ���Ͽ� vertex�� ���� loop�� ���� ���մϴ�.
    
    vertex ���� vertices�� �ҷ������ν� �ʱⰪ�� �����ϸ�, transformation pipeline�� ����� �� vertex ���� �ٽ� ����ؼ� vertices�� �����մϴ�.
    ```
    for (int i = 0; i < gNumVertices; i++) {
        // get vertices from vertices array
        vec4 vertex(vertices[i].x, vertices[i].y, vertices[i].z, 1);
        
        // transformation pipeline
        mat4 mtx = transformation_pipeline(camera);

        // multiply the transformation matrix with the vertex
        vertex = multipl_mtx_vec(mtx, vertex);

        // normalize vertex values
        vertex.x = vertex.x / vertex.w;
        vertex.y = vertex.y / vertex.w;
        vertex.z = vertex.z / vertex.w;
        vertex.w = vertex.w / vertex.w;

        // put normalized values back to the vertices array
        vertices[i].x = vertex.x;
        vertices[i].y = vertex.y;
        vertices[i].z = vertex.z;
    }
    ```

    ���� for loop�� ���� ������ �ﰢ���� ���Ͽ� 3 ���� �������� ���� ��ǥ�� ã���ϴ�.
    �� �������� point_a, point_b, point_c�� �̸��� �ٿ����ϴ�.

    xmin, xmax, ymin, ymax ���� ���Ͽ� �ﰢ���� ���� bounding box�� �����ϰ�, �� ���� ���Ͽ� beta�� gamma ���� ���մϴ�.

    beta_x�� x�� ���������� beta�� ����, beta_y�� y�� ���������� beta�� ���⸦ �ǹ��ϹǷ� �� ���⿡ ���� ���⸦ ���մϴ�.
    gamma_x�� gamma_y�� ���ؼ��� ���������� ���մϴ�.

    ���� int n ���� �����ϰ�, for loop�� ���� beta�� gamma ���� ���캸�� �ﰢ�� mesh ���� ���� �ȼ��� ���� ������� ĥ�մϴ�.

    beta ���� gamma ���� for loop�� ���� ���ذ��ϴ�.
    
    �̸� �� ��ü�� �����ϴ� �ﰢ�� mesh�� ���Ͽ� ���� �ݺ����ָ� ���� �׸� �� �ֽ��ϴ�.
    ```
    for (int i = 0; i < gNumTriangles; i++) {
        // index of the vertices of the triangle
        int k0 = gIndexBuffer[3 * i];
        int k1 = gIndexBuffer[3 * i + 1];
        int k2 = gIndexBuffer[3 * i + 2];

        // get the vertices of the triangle
        vec3 point_a = vec3(vertices[k0]);
        vec3 point_b = vec3(vertices[k1]);
        vec3 point_c = vec3(vertices[k2]);

        // get bounding box of the triangle
        int xmin = std::min(std::min(point_a.x, point_b.x), point_c.x);
        int xmax = std::max(std::max(point_a.x, point_b.x), point_c.x);
        int ymin = std::min(std::min(point_a.y, point_b.y), point_c.y);
        int ymax = std::max(std::max(point_a.y, point_b.y), point_c.y);

        // starting point of each beta and gamma
        float beta = ((point_a.y - point_c.y) * xmin + (point_c.x - point_a.x) * ymin + point_a.x * point_c.y - point_c.x * point_a.y) / ((point_a.y - point_c.y) * point_b.x + (point_c.x - point_a.x) * point_b.y + point_a.x * point_c.y - point_c.x * point_a.y);
        float gamma = ((point_a.y - point_b.y) * xmin + (point_b.x - point_a.x) * ymin + point_a.x * point_b.y - point_b.x * point_a.y) / ((point_a.y - point_b.y) * point_c.x + (point_b.x - point_a.x) * point_c.y + point_a.x * point_b.y - point_b.x * point_a.y);

        // increasing value of beta and gamma in each axis
        float beta_x = (point_a.y - point_c.y) / ((point_a.y - point_c.y) * point_b.x + (point_c.x - point_a.x) * point_b.y + point_a.x * point_c.y - point_c.x * point_a.y);
        float beta_y = (point_c.x - point_a.x) / ((point_a.y - point_c.y) * point_b.x + (point_c.x - point_a.x) * point_b.y + point_a.x * point_c.y - point_c.x * point_a.y);

        float gamma_x = (point_a.y - point_b.y) / ((point_a.y - point_b.y) * point_c.x + (point_b.x - point_a.x) * point_c.y + point_a.x * point_b.y - point_b.x * point_a.y);
        float gamma_y = (point_b.x - point_a.x) / ((point_a.y - point_b.y) * point_c.x + (point_b.x - point_a.x) * point_c.y + point_a.x * point_b.y - point_b.x * point_a.y);

        int n = (xmax - xmin) + 1;

        for (int y = ymin; y <= ymax; y++) {
            for (int x = xmin; x <= xmax; x++) {
                if(beta > 0 && gamma > 0 && beta + gamma < 1) {
                    int idx = (y * Ny + x) * 3;
                    image[idx] = 255;
                    image[idx + 1] = 255;
                    image[idx + 2] = 255;
                }
                beta += beta_x;
                gamma += gamma_x;
            }
            beta += beta_y - n * beta_x;
            gamma += gamma_y - n * gamma_x;
        }   
    }
    ```

    ���� glDrawPixels(Nx, Ny, GL_RGB, GL_UNSIGNED_BYTE, image); �� ���� �̹����� ����մϴ�.
---

## �����մϴ�.

##### ������: �Ǳ����б� ���п� ��ǻ�Ͱ��а� 202371451 ������