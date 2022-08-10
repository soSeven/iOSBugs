### iOS14获取iCloud视频失败问题

1. 使用`Photos`框架的`requestAVAssetForVideo`方法获取在`iCloud`视频时获取失败
   
   ```swift
   let option = PHVideoRequestOptions()
   option.version = .original
   /// `PHVideoRequestOptionsDeliveryMode` 必须为 `highQualityFormat`
   /// 不然可能获取不到iCloud视频
   option.deliveryMode = .highQualityFormat
   option.isNetworkAccessAllowed = true
   ```

2.  `AVAssetExportSession `进行压缩发现压缩失败
   
   ```swift
   /// AVAssetExportSession压缩视频的outputURL参数
   /// 要使用`URL(fileURLWithPath: path)`
   let outputURL = URL(fileURLWithPath: path)
   ```


