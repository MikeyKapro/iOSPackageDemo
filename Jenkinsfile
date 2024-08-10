library "pipeline-iOS-library"
import org.apache.commons.collections4.map.LinkedMap

def map = [:]
// App的名称
map.put('appName','YourAppNmae')
// 上传OSS的主路径
map.put('uploadOSSMainPath','oss://yourBucketName/****/YourAppNmae')
// 下载OSS的主路径，也是图片存放的路径
map.put('downloadOSSImageMainPath','https://*******/YourAppNmae')
// iOS项目地址
map.put('useRepository','https://***************.git')
// App小图标URL，图片尺寸57x57像素
map.put('dispalyImageUrl','https://***************/*****.png')
// App大图标URL，图片尺寸512x512像素
map.put('fullSizeImageUrl','https://**************/*****.png')
// 阿里云OSS上传文件的执行文件的地址（这里不用改）
map.put('ossUploadToolPath','ossutil')

/*
列表第一个元素：configuration的描述
列表第二个元素：构建时的命令，如：fastlane qa
添加跟configuration相关的信息
列表第三个元素：是否显示下载用QRCode
列表第四个元素：是否将build号修改为构建时间
*/
def configurationMap = new LinkedMap()
String enterpriseName = "Enterprise"
configurationMap.put("QA", ["QA：测试、产品、UI、翻译人员使用", "fastlane qa", true, true])
configurationMap.put("TestFlight", ["TestFlight：TF签，开发人员使用", "fastlane tf", false, false]) // TF签不需要ipa二维码，因为给的是App Store的证书
configurationMap.put((enterpriseName), ["${enterpriseName}：企业签，开发人员使用", "fastlane enterprise", true, false])
configurationMap.put("Super", ["Super：超级签，开发人员使用", "fastlane super", true, false])

// 企业签的证书集合（内容填写证书名称）
List enterpriseCertificateList = ["CertificateName1", "CertificateName2", "CertificateName3"]

/*
通知方式
列表第一个元素：0-MicrosoftTeams 1-钉钉（钉钉暂不支持）
列表第二个元素：对应通知的地址
*/
def notificationMap = new LinkedMap()
notificationMap.put("发送到Teams测试群", [0, "https://********"])
notificationMap.put("发送到TeamsiOS发布群", [0, "https://********"])

iOSPackage(map, configurationMap, notificationMap, enterpriseName, enterpriseCertificateList)