
# Apache TVM v0.8dev for Google Colab

```
# from https://colab.research.google.com/github/uwsampl/tutorial/blob/master/notebook/02_TVM_Tutorial_Relay.ipynb#scrollTo=bdiA6WVx0Nuc
try:
  import google.colab
  IN_COLAB = True
except:
  IN_COLAB = False

if IN_COLAB:
    # Installing Dependencies
    !sudo apt-get update -qq
    !sudo apt-get install -y -q \
        git \
        cmake \
        build-essential \
        libtinfo-dev \
        libffi-dev \
        zlib1g-dev \
        llvm-15-dev \
        libclang-15-dev \
        ninja-build # Ninja can speed up compilation if available

    ! wget -O /tmp/tvm.zip https://github.com/Ethan-a2/TVM_colab/raw/master/build/python.zip
    ! mkdir -p /tvm
    ! unzip "/tmp/tvm.zip" -d /tmp/ && cp -r /tmp/python /tvm
    ! ls -la /tvm

    # Add TVM to the Python path.
    import sys
    import os
    sys.path.append('/tvm/python')
    os.environ['TVM_HOME'] = '/tvm'
    import tvm
    print(f"TVM Python Package Version: {tvm.__version__}")

else:
    print("Notebook executing locally, skipping Colab setup ...")
```

# references

https://github.com/sebinthomas/TVM_colab/tree/master
