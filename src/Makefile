ROOT_DIR=/Users/kramer/Desktop/kinect-osx/src/
INCLUDE_DIRS=-I$(ROOT_DIR)pcl/include/pcl-1.6/ -I$(ROOT_DIR)pcl/include/eigen3 -I$(ROOT_DIR)pcl/include/
LIBRARY_DIR=-L$(ROOT_DIR)pcl/lib/osx
LIBRARIES=-lpcl_io -lpcl_common -lpcl_features -lpcl_filters -lpcl_geometry -lpcl_io_ply -lpcl_kdtree -lpcl_keypoints -lpcl_octree -lpcl_registration -lpcl_sample_consensus -lpcl_search -lpcl_segmentation -lpcl_surface -lpcl_tracking -lboost_date_time-mt -lboost_filesystem-mt -lboost_iostreams-mt -lboost_system-mt -lboost_thread-mt
LD_LIBRARY_PATH=$ROOT_DIR/pcl/lib/osx
CC_FLAGS=-w -arch i386 -j4
DYLD_LIBRARY_PATH=$(ROOT_DIR)pcl/lib/osx


SRCS = PointCloud.cpp PointCloudPairRegistration.cpp registerPointCloudsApp.cpp
OBJS = $(SRCS:.cpp=.o)

all: kinect
	echo Done

kinect: $(OBJS)
	g++ $(CC_FLAGS) $(LIBRARY_DIR) $(LIBRARIES) -rpath $(DYLD_LIBRARY_PATH) $^ -o ../$@

%.o: %.cpp
	g++ $(CC_FLAGS) $(INCLUDE_DIRS) -c $<

clean:
	rm -f $(OBJS) kinect