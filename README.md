# myConkyStyle
This is a conky configuration for linux OS <br>
<B> Please make sure you are using the latest version of conky <B>

![Image of my conky](https://github.com/godsamix/myConkyStyle/blob/main/conkyimg.jpg)


```
conky.config = {
  alignment = 'top_right',
xinerama_head = 2,
  background = false,
  border_width = 0.5,
  cpu_avg_samples = 4,
  default_color = 'white',
  default_outline_color = 'grey',
  default_shade_color = 'black',
  draw_borders = true,
  draw_graph_borders = true,
  draw_outline = false,
  draw_shades = false,
  use_xft = true,
  font = 'DejaVu Sans Mono:size=10',
  gap_x = 10,
  gap_y = 10,
  maximum_width = 250,
  minimum_height = 5,
  minimum_width = 5,
  net_avg_samples = 2,
  double_buffer = true,
  out_to_console = false,
  out_to_stderr = false,
  extra_newline = false,
  own_window = true,
  own_window_colour = '000000',
  own_window_class = 'Conky',
  own_window_argb_visual = true,
  own_window_type = 'dock',
  own_window_transparent = true,
  own_window_hints = 'undecorated,below,sticky,skip_taskbar,skip_pager',
  stippled_borders = 0,
  update_interval = 1,
  uppercase = false,
  use_spacer = 'none',
  show_graph_scale = false,
  show_graph_range = false
}

conky.text = [[
${color #B66DFF}${font}${font Open Sans:size=30}$alignr${time %H:%M}$font$color${font Open Sans:size=15}
${color #B66DFF}$alignr${time %a}, ${time %d %b %Y}$font$color
${font Open Sans:Bold:size=15}${color #B66DFF} GodSamix
${font Open Sans:Bold:size=10}${color #FF994E}SYSTEM ${hr 2}$color${font}${offset 1}
${color #FF994E}Kernel ${color1}$alignr $kernel
${color #FF994E}Uptime ${color1}$alignr $uptime

# Intel CPU
${font Open Sans:Bold:size=10}${color 46B3F3}CPU ${hr 2}$color${font}
${color 46B3F3}${font FontAwesome} ${font}${lua processor} ${color 46B3F3}CPU Freq: ${color1}$alignr $freq_g GHz
${color 46B3F3}${font}Usage: ${color1} $alignr $cpu %
${color 46B3F3}Temperature: ${color1} $alignr ${acpitemp}°C
$font${color #46B3F3}Core1 ${color1}${cpu cpu1}% ${cpubar cpu1}
${color #46B3F3}Freq: ${color1} ${freq 1}MHz
${color #46B3F3}Core2 ${color1}${cpu cpu2}% ${cpubar cpu2}
${color #46B3F3}Freq: ${color1} ${freq 2}MHz
${color #46B3F3}Core3 ${color1}${cpu cpu3}% ${cpubar cpu3}
${color #46B3F3}Freq: ${color1} ${freq 3}MHz
${color #46B3F3}Core4 ${color1}${cpu cpu4}% ${cpubar cpu4}
${color #46B3F3}Freq: ${color1} ${freq 4}MHz
${color #46B3F3}Core5 ${color1}${cpu cpu5}% ${cpubar cpu5}
${color #46B3F3}Freq: ${color1} ${freq 5}MHz
${color #46B3F3}Core6 ${color1}${cpu cpu6}% ${cpubar cpu6}
${color #46B3F3}Freq: ${color1} ${freq 6}MHz

${font Open Sans:Bold:size=10}${color #73B761}GPU NVIDIA ${hr 2}$color${font}
${color #73B761}GPU 0: ${color1}${exec nvidia-smi -i 0 --query-gpu=gpu_name --format=csv,noheader,nounits} $color
${color #73B761}Temperature: ${color1}  ${execi 60 nvidia-settings -query [gpu:0]/GPUCoreTemp -t} °C
${color #73B761}Utilization: ${color1}  ${exec nvidia-smi -i 0 | grep % | cut -c 61-63} %
${color #73B761}VRAM Utilization: ${color1} ${exec nvidia-smi -i 0| grep % | cut -c 37-40} MB
${color #73B761}Power Draw: ${color1} ${exec nvidia-smi -i 0| grep % | cut -c 21-23} W

# RAM
${font Open Sans:Bold:size=10}${color #FEB5DA}RAM ${hr 2}$color${font}
${color FEB5DA}Total: ${color1}$alignr $memmax
${color FEB5DA}In use: ${color1}$alignr $mem
${color FEB5DA}Free: ${color1}$alignr $memeasyfree
$font${color FEB5DA}MEM: ${color1}$alignc $mem / $memmax $alignr $memperc%
${color FEB5DA}$membar

${font Arial:bold:size=10}${color #ECC846}HDD ${color #ECC846}${hr 2}
$font${color ECC846}/KALI ${color1}$alignc ${fs_used /} / ${fs_size /} $alignr ${fs_free_perc /}%
${color #ECC846}${fs_bar /}
${color #ECC846}Disk I/O: ${color1}${diskio}
${color ECC846}Read:
${color DimGray}${diskiograph_read 20,250 FF0033 FF0033 750}
${color ECC846}Write:
${color DimGray}${diskiograph_write 20,250 66FF33 66FF33 750}

${font Arial:bold:size=10}${color #42F9F9}NETWORK ${color #42F9F9}${hr 2}
${color #42F9F9}Public IP: $alignr${color1}${execi 60 curl  ipinfo.io/ip}
${color #42F9F9}Private IP: $alignr${color1}${addr wlan0}
#$font${color #66FF33}IP on wlan0 $alignr ${addr wlan0}
$font${color 42F9F9}Up $alignr ${color #FF0033}${upspeed wlan0}
${color DimGray}${upspeedgraph wlan0 20,250 FF0033 FF0033}
${color 42F9F9}Down $alignr ${color #66FF33}${downspeed wlan0}
${color DimGray}${downspeedgraph wlan0 20,250 66FF33 66FF33}  
${color FF0033}UP: $alignr ${totalup wlan0}${color #66FF33} DOWN: $alignr ${totaldown wlan0}

]]
```
