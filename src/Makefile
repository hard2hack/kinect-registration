ROOT_DIR=./
INCLUDE_DIRS=-I /usr/include/eigen3/ -I /usr/include/pcl-1.6/ -I /usr/include/
LIBRARY_DIR=-L/usr/lib
LIBRARIES=-lpcl_apps -lpcl_io -lpcl_segmentation -lpcl_common -lpcl_kdtree -lpcl_surface -lpcl_features -lpcl_keypoints -lpcl_registration -lpcl_filters -lpcl_octree -lpcl_sample_consensus -lpcl_visualization -lpcl_io_ply -lpcl_search
CC_FLAGS=-w

SRCS = PointCloud.cpp PointCloudPairRegistration.cpp registerPointCloudsApp.cpp
OBJS = $(SRCS:.cpp=.o)

all: kinect
	echo Done

kinect: $(OBJS)
	g++ $(CC_FLAGS) $^ -o ../$@ $(LIBRARY_DIR) $(LIBRARIES)

%.o: %.cpp
	g++ $(CC_FLAGS) $(INCLUDE_DIRS) -c $<

clean:
	rm -f $(OBJS) ../kinect
