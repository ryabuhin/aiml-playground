FROM rocm/pytorch:latest

RUN git clone https://github.com/ggml-org/llama.cpp.git /llama.cpp
WORKDIR /llama.cpp
RUN HIPCXX="$(hipconfig -l)/clang" HIP_PATH="$(hipconfig -R)" \
cmake -S . -B build -DGGML_HIP=ON -DAMDGPU_TARGETS=gfx1030 -DCMAKE_BUILD_TYPE=Release \
&& cmake --build build --config Release -- -j 16

ENV PATH="$PATH:/llama.cpp/build/bin"