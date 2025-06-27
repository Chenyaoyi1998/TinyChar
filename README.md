# TinyChar
TinyChar： 使用动态视觉传感器采集的微小物体检测数据集。     
我们制作了一个DVS数据集 TinyChar，分辨率720x1000，它包含32段事件流，共计大约180秒，以2Hz的频率标记了20种共6539个边界框，每个边界框的尺寸在15x15左右，使用PROPHESEE EVK4拍摄。 

![image/example1.jpg](https://github.com/Chenyaoyi1998/TinyChar/blob/main/Image/example1.jpg)    
![image/example0.jpg](https://github.com/Chenyaoyi1998/TinyChar/blob/main/Image/example0.jpg)

# 数据集格式
事件流片段：filename_cd.dat    
边界框标注：filename_bbox.txt

# 边界框格式
x y w h class timestamp    
x和y为左上角坐标

# 加载.dat文件
可以使用PROPHESEE提供的工具包处理    
```
from src.io.psee_loader import PSEELoader

cd_loader = PSEELoader(cd_file)
cd_events_num = cd_loader.event_count()
cd_events_time = cd_loader.total_time()
events = dat_event.load_n_events(int(end_count - start_count))
```
