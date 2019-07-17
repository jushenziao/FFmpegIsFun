av_register_all()//所有的ffmpeg程序都需要

avformat_open_input() /avformat_close_input()

av_dump_format()



打印音视频meidiainfo

\#include <libavutil/log.h>

\#include <libavformat/avformat.h>



int main(int argc,char* argv[]){



​        int ret;

​        AVFormatContext *fmt_ctx = NULL;

​        av_log_set_level(AV_LOG_INFO);

​        av_register_all();

​        ret = avformat_open_input(&fmt_ctx,"./test.mp4",NULL,NULL);

​        if(ret <0){

​        av_log(NULL,AV_LOG_ERROR,"CAN not open filr :%s\n",av_err2str(ret));

​        }

​        av_dump_format(fmt_ctx,0,"./test.mp4",0);

​        avformat_close_input(&fmt_ctx);

​        return 0;

}