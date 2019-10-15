<template>
  <div>
    <div style="margin: 5px 0">
      <el-button type="primary" :loading="downloadLoading" @click="exportAllData">导出全部数据</el-button>
      <el-button type="success" :loading="downloadLoading" @click="exportSelectedData">导出已选数据</el-button>
    </div>
    <el-table ref="multipleTable" :data="list" border highlight-current-row>
      <el-table-column type="selection"width="55"></el-table-column>
      <el-table-column prop="productId" label="产品编号"></el-table-column>
      <el-table-column prop="partnerName" label="合作方名称"></el-table-column>
      <el-table-column prop="fundName" label="资金方名称"></el-table-column>
      <el-table-column prop="model" label="合作模式"></el-table-column>
      <el-table-column prop="productType" label="产品类别"></el-table-column>
      <el-table-column prop="firstProduct" label="一级产品"></el-table-column>
      <el-table-column prop="statusText" label="产品状态"></el-table-column>
    </el-table>
  </div>
</template>

<script>
export default {
  name: 'Table',
  data() {
    return {
      downloadLoading: false,
      selectionList: [],
      list: [
        {
          "partnerName": "稠州银行",
          "partnerId": "RP20161214000001",
          "fundName": "稠州银行",
          "fundId": "RL20161214000001",
          "model": "大数融资担保+紫金保险",
          "modelId": "RDZJBX",
          "productType": "信用贷款",
          "productTypeId": "01",
          "firstProduct": "大数V贷",
          "firstProductId": "050",
          "version": "V2-1.0.0",
          "status": "published",
          "statusText": "已发布",
          "isInuse": "1",
          "isInuseText": "有效",
          "updatedBy": "EX-CHENXIEHUI",
          "updatedDate": "2019-10-14 14:04:24",
          "createdBy": "EX-CHENXIEHUI",
          "createdDate": "2019-10-14 14:04:15",
          "productId": "P20191014000003"
        },
        {
          "partnerName": "稠州银行",
          "partnerId": "RP20161214000001",
          "fundName": "稠州银行",
          "fundId": "RL20161214000001",
          "model": "大数融资担保+紫金保险",
          "modelId": "RDZJBX",
          "productType": "信用贷款",
          "productTypeId": "01",
          "firstProduct": "大数时贷",
          "firstProductId": "010",
          "version": "V2-1.0.0",
          "status": "published",
          "statusText": "已发布",
          "isInuse": "1",
          "isInuseText": "有效",
          "updatedBy": "EX-CHENXIEHUI",
          "updatedDate": "2019-10-14 14:02:44",
          "createdBy": "EX-CHENXIEHUI",
          "createdDate": "2019-10-14 14:02:33",
          "productId": "P20191014000002"
        },
        {
          "partnerName": "大地产险-徽商银行",
          "partnerId": "RP20181227028932",
          "fundName": "徽商银行",
          "fundId": "RL20181227028932",
          "model": "大数金融",
          "modelId": "DSF",
          "productType": "信用贷款",
          "productTypeId": "01",
          "firstProduct": "发票贷",
          "firstProductId": "110",
          "version": "V1-1.0.0",
          "status": "published",
          "statusText": "已发布",
          "isInuse": "1",
          "isInuseText": "有效",
          "updatedBy": "HUANGBAOHUA",
          "updatedDate": "2019-10-12 14:53:12",
          "createdBy": "DUBIN",
          "createdDate": "2019-10-11 16:56:07",
          "productId": "P20191011000018"
        },
        {
          "partnerName": "大地产险-徽商银行",
          "partnerId": "RP20181227028932",
          "fundName": "徽商银行",
          "fundId": "RL20181227028932",
          "model": "大数金融",
          "modelId": "DSF",
          "productType": "信用贷款",
          "productTypeId": "01",
          "firstProduct": "大数时贷",
          "firstProductId": "010",
          "version": "1.0.1",
          "status": "published",
          "statusText": "已发布",
          "isInuse": "1",
          "isInuseText": "有效",
          "updatedBy": "HUANGBAOHUA",
          "updatedDate": "2019-10-12 14:53:10",
          "createdBy": "LIJINGMEI",
          "createdDate": "2019-05-05 11:20:24",
          "productId": "P20190429000001"
        },
        {
          "partnerName": "大地产险-徽商银行",
          "partnerId": "RP20181227028932",
          "fundName": "徽商银行",
          "fundId": "RL20181227028932",
          "model": "大数金融",
          "modelId": "DSF",
          "productType": "信用贷款",
          "productTypeId": "01",
          "firstProduct": "大数V贷",
          "firstProductId": "050",
          "version": "1.0.1",
          "status": "published",
          "statusText": "已发布",
          "isInuse": "1",
          "isInuseText": "有效",
          "updatedBy": "HUANGBAOHUA",
          "updatedDate": "2019-10-12 14:53:07",
          "createdBy": "LIJINGMEI",
          "createdDate": "2019-05-05 11:30:31",
          "productId": "P20190429000002"
        },
        {
          "partnerName": "大地产险-徽商银行",
          "partnerId": "RP20181227028932",
          "fundName": "徽商银行",
          "fundId": "RL20181227028932",
          "model": "大数金融",
          "modelId": "DSF",
          "productType": "信用贷款",
          "productTypeId": "01",
          "firstProduct": "无忧贷",
          "firstProductId": "120",
          "version": "V1-1.0.0",
          "status": "published",
          "statusText": "已发布",
          "isInuse": "1",
          "isInuseText": "有效",
          "updatedBy": "HUANGBAOHUA",
          "updatedDate": "2019-10-12 14:53:03",
          "createdBy": "DUBIN",
          "createdDate": "2019-10-11 16:35:32",
          "productId": "P20191011000015"
        },
        {
          "partnerName": "大地产险",
          "partnerId": "RP20181227028932",
          "fundName": "徽商银行",
          "fundId": "RL20181227028932",
          "model": "大数金融",
          "modelId": "DSF",
          "productType": "信用贷款",
          "productTypeId": "01",
          "firstProduct": "发票贷",
          "firstProductId": "110",
          "version": "V1-1.0.0",
          "status": "published",
          "statusText": "已发布",
          "isInuse": "1",
          "isInuseText": "有效",
          "updatedBy": "DUBIN",
          "updatedDate": "2019-10-12 14:32:21",
          "createdBy": "DUBIN",
          "createdDate": "2019-10-12 14:30:07",
          "productId": "P20191012000004"
        },
        {
          "partnerName": "大地产险",
          "partnerId": "RP20181227028932",
          "fundName": "徽商银行",
          "fundId": "RL20181227028932",
          "model": "大数金融",
          "modelId": "DSF",
          "productType": "信用贷款",
          "productTypeId": "01",
          "firstProduct": "大数时贷",
          "firstProductId": "010",
          "version": "V1-1.0.0",
          "status": "published",
          "statusText": "已发布",
          "isInuse": "1",
          "isInuseText": "有效",
          "updatedBy": "DUBIN",
          "updatedDate": "2019-10-12 14:26:43",
          "createdBy": "DUBIN",
          "createdDate": "2019-10-12 14:20:21",
          "productId": "P20191012000002"
        },
        {
          "partnerName": "大地产险",
          "partnerId": "RP20181227028932",
          "fundName": "徽商银行",
          "fundId": "RL20181227028932",
          "model": "大数金融",
          "modelId": "DSF",
          "productType": "信用贷款",
          "productTypeId": "01",
          "firstProduct": "无忧贷",
          "firstProductId": "120",
          "version": "V1-1.0.0",
          "status": "published",
          "statusText": "已发布",
          "isInuse": "1",
          "isInuseText": "有效",
          "updatedBy": "DUBIN",
          "updatedDate": "2019-10-12 14:25:29",
          "createdBy": "DUBIN",
          "createdDate": "2019-10-12 14:20:21",
          "productId": "P20191012000001"
        },
        {
          "partnerName": "大地产险",
          "partnerId": "RP20181227028932",
          "fundName": "徽商银行",
          "fundId": "RL20181227028932",
          "model": "大数金融",
          "modelId": "DSF",
          "productType": "信用贷款",
          "productTypeId": "01",
          "firstProduct": "大数V贷",
          "firstProductId": "050",
          "version": "V1-1.0.0",
          "status": "published",
          "statusText": "已发布",
          "isInuse": "1",
          "isInuseText": "有效",
          "updatedBy": "DUBIN",
          "updatedDate": "2019-10-12 14:25:23",
          "createdBy": "DUBIN",
          "createdDate": "2019-10-12 14:20:22",
          "productId": "P20191012000003"
        }
      ]
    }
  },
  methods: {
    /**
     * 导出表格数据
     * @param tableRef 表格引用对象，在 vue 组件上添加 ref 属性 ref="abc"，即可通过 this.$refs.abc 获取此组件的引用
     * @param filename 导出的文件名,不需要带后缀
     * @param selection 标记是导出全部数据还是导出已选择数据，布尔值。true：导出已选数据；false或不写此参数：导出表格全部数据
     */
    exportExcel(tableRef, filename, selection) {
      this.downloadLoading = true
      // 采用动态导入
      import('@/utils/Export2Excel').then(excel => {
        excel.export_table_to_excel({ tableRef, filename, selection })
        this.downloadLoading = false
      })
    },
    /**
     * 导出表格已加载的所有数据
     */
    exportAllData() {
      // this.$refs.multipleTable 对应 <el-table> 组件的属性： ref="multipleTable" 
      this.exportExcel(this.$refs.multipleTable, `导出全部数据-${new Date().getTime()}`)
    },
    /**
     * 导出表格已选择数据
     */
    exportSelectedData() {
      // this.$refs.multipleTable 对应 <el-table> 组件的属性： ref="multipleTable" 
      this.exportExcel(this.$refs.multipleTable, `导出选择数据-${new Date().getTime()}`, true)
    },
  }
}
</script>


<style scoped>
</style>
