<template>
  <a-layout class="layout" style="min-height: 100vh">
    <a-layout-header>
      <a-layout-header style=" padding: 2px">
        <div class="logo">
          <img class="head-img" height="60" src="../assets/logo-ow-bg3.png"/>
        </div>
      </a-layout-header>
    </a-layout-header>
    <a-layout-content style="padding: 18px 50px">
      <div style="padding: 20px;">
        <a-row :gutter="16">
          <a-col :span="14">
            <a-card title="图信息" :bordered="false" class="info-card" >
              <div style="background-color: #ececec; padding: 10px ;">
                <a-row :gutter="16">
                  <a-col :span="24">
                    <a-card :bordered="false">


                      <a-descriptions title="查询图信息" style="display: flex; flex-direction: column;" colon="false">
                        <a-descriptions-item label="节点个数">Zhou Maomao</a-descriptions-item>
                        <a-descriptions-item label="边个数">1810000000</a-descriptions-item>
                        <a-descriptions-item label="节点最大度">Hangzhou, Zhejiang</a-descriptions-item>
                      </a-descriptions>
                    </a-card>
                  </a-col>
                  <a-col :span="24">
                    <a-card :bordered="false" :style="{ marginTop: '16px' }">
                      <a-descriptions title="数据图信息">
                        <a-descriptions-item label="节点个数">Zhou Maomao</a-descriptions-item>
                        <a-descriptions-item label="边个数">1810000000</a-descriptions-item>
                        <a-descriptions-item label="节点最大度">Hangzhou, Zhejiang</a-descriptions-item>
                      </a-descriptions>
                    </a-card>
                  </a-col>
                </a-row>
              </div>
            </a-card>
          </a-col>
          <a-col :span="10">
            <a-row :gutter="16">
              <a-col :span="24">
                <a-card title="运行结果" :bordered="false">
                  <a-row :gutter="16">
                    <a-col :span="12">
                      <a-card>
                        <a-statistic
                            title="匹配数量"
                            :value="11.28"
                            :precision="2"
                            suffix="%"
                            :value-style="{ color: '#3f8600' }"
                            style="margin-right: 50px"
                        >
                          <template #prefix>
                            <arrow-up-outlined/>
                          </template>
                        </a-statistic>
                      </a-card>
                    </a-col>
                    <a-col :span="12">
                      <a-card>
                        <a-statistic
                            title="运行时间"
                            :value="9.3"
                            :precision="2"
                            suffix="%"
                            class="demo-class"
                            :value-style="{ color: '#cf1322' }"
                        >
                          <template #prefix>
                            <arrow-down-outlined/>
                          </template>
                        </a-statistic>
                      </a-card>
                    </a-col>
                  </a-row>

                  <a-row justify="center" style="padding-top: 18px">
                    <a-button type="primary">点击下载匹配结果文件</a-button>
                  </a-row>

                </a-card>
              </a-col>
            </a-row>
            <div style="height: 16px"></div> <!-- 添加间隔 -->
            <a-row :gutter="16" style="height: 100%">
              <a-col :span="24">
                <a-card title="图文件" :bordered="false">
                  <a-form
                      :label-col="{ span: 5 }"
                      :wrapper-col="{ span: 15 }"
                      layout="horizontal"
                  >
                    <a-form-item label="上传查询图">
                      <a-upload-dragger
                          v-model:fileList="fileList"
                          name="file1"
                          :before-upload="beforeUpload"
                          action="https://www.mocky.io/v2/5cc8019d300000980a055e76"

                      >
                        <p class="ant-upload-drag-icon">
                          <inbox-outlined></inbox-outlined>
                        </p>
                        <p class="ant-upload-text">查询图</p>
                        <p class="ant-upload-hint">
                          点击或拖动文件至此区域上传
                        </p>
                      </a-upload-dragger>
                    </a-form-item>

                    <a-form-item label="上传数据图">
                      <a-upload-dragger
                          v-model:fileList="fileList2"
                          name="file2"
                          :before-upload="beforeUpload"
                          action="https://www.mocky.io/v2/5cc8019d300000980a055e76"
                      >
                        <p class="ant-upload-drag-icon">
                          <inbox-outlined></inbox-outlined>
                        </p>
                        <p class="ant-upload-text">数据图</p>
                        <p class="ant-upload-hint">
                          点击或拖动文件至此区域上传
                        </p>
                      </a-upload-dragger>
                    </a-form-item>
                  </a-form>
                  <a-row justify="center" style="padding-top: 18px">
                    <a-button type="primary">开始匹配</a-button>
                  </a-row>
                </a-card>
              </a-col>
            </a-row>
          </a-col>
        </a-row>
      </div>
    </a-layout-content>
    <a-layout-footer style="text-align: center">
      Ant Design ©2018 Created by Ant UED
    </a-layout-footer>
  </a-layout>
</template>
<script setup>
import {ref} from 'vue';

const beforeUpload = file => {
  const fileList = ref([]);
  fileList.value = [...(fileList.value || []), file];
  return false;
};
</script>
<style scoped>
.site-layout-content {
  min-height: 280px;
  padding: 24px;
  background: #fff;
}

#components-layout-demo-top .logo {
  float: left;
  width: 120px;
  height: 31px;
  margin: 16px 24px 16px 0;
  background: rgba(255, 255, 255, 0.3);
}

.ant-row-rtl #components-layout-demo-top .logo {
  float: right;
  margin: 16px 0 16px 24px;
}

[data-theme='dark'] .site-layout-content {
  background: #141414;
}

.info-card {
  padding: 20px;
}

.section-title {
  font-size: 18px;
  font-weight: bold;
  margin-bottom: 10px;
}
</style>
