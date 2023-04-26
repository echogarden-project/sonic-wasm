PROJ=sonic

EMCCFLAGS=-s WASM=1 -s ALLOW_MEMORY_GROWTH=1 -s MAXIMUM_MEMORY=4GB -s MALLOC='emmalloc' -s EXPORTED_FUNCTIONS="['_malloc', '_free', '_sonicCreateStream', '_sonicDestroyStream', '_sonicWriteFloatToStream', '_sonicWriteShortToStream', '_sonicWriteUnsignedCharToStream', '_sonicReadFloatFromStream', '_sonicReadShortFromStream', '_sonicReadUnsignedCharFromStream', '_sonicFlushStream', '_sonicSamplesAvailable', '_sonicGetSpeed', '_sonicSetSpeed', '_sonicGetPitch', '_sonicSetPitch', '_sonicGetRate', '_sonicSetRate', '_sonicGetVolume', '_sonicSetVolume', '_sonicGetQuality', '_sonicSetQuality', '_sonicGetSampleRate', '_sonicSetSampleRate', '_sonicGetNumChannels', '_sonicSetNumChannels', '_sonicChangeFloatSpeed', '_sonicChangeShortSpeed']" -s EXPORTED_RUNTIME_METHODS="['getValue', 'setValue', 'cwrap']" -s MODULARIZE=1 -s EXPORT_NAME="Sonic"

all: sonic.c
	emcc $(EMCCFLAGS) -O3 -o $(PROJ).cjs $^

.PHONY: clean
clean:
	rm -f $(PROJ).cjs $(PROJ).wasm
