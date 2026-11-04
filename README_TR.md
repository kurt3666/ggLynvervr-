# ggLynvervr Android başlangıç projesi

Bu paket, Kotlin + Jetpack Compose arayüz iskeletini ve TDLib Android bağımlılıklarını içerir.

## Önemli not
- Bu ilk sürüm açılış/arayüz iskeletidir; Telegram giriş ve sohbet akışı henüz bağlanmış değildir.
- TDLib AAR bağımlılığı `io.github.tdlib-android` adlı topluluk dağıtımıdır; Telegram'ın resmî Android SDK paketi değildir. Üretime geçmeden önce sürüm, kaynak kod, lisans ve ikili dosyaları denetleyin.
- Resmî TDLib Android derlemesi CMake/NDK ile native kütüphaneleri üretir. Resmî talimat: https://github.com/tdlib/td/blob/master/example/android/README.md
- API hash'inizi sohbete, herkese açık depoya veya kaynak koda koymayın.

## GitHub ile telefondan APK
1. GitHub hesabı açın: https://github.com/signup
2. Yeni bir **Private** repository oluşturun: `ggLynvervr`.
3. Bu ZIP'i telefonda çıkarın.
4. İçindeki dosya ve klasörleri repository ana dizinine yükleyin. `.github/workflows/android.yml` klasörünün de yüklendiğini kontrol edin.
5. GitHub repository > Settings > Secrets and variables > Actions > New repository secret:
   - `TELEGRAM_API_ID` = my.telegram.org'dan aldığınız sayısal api_id
   - `TELEGRAM_API_HASH` = api_hash
6. Actions sekmesine girin > `Build ggLynvervr APK` > Run workflow.
7. İşlem başarılı olunca workflow çalışmasının altındaki Artifacts bölümünden `ggLynvervr-debug-apk` dosyasını indirin.
8. ZIP'i çıkarın ve `app-debug.apk` dosyasını Android'e kurun.

## Yerel derleme
Android Studio/Gradle ve Android SDK gerekir. Telefon üzerinden GitHub Actions yöntemi daha kolaydır.

## Sonraki geliştirme
TDLib `TdClient` API'sini kullanarak authorization state, telefon numarası, kod ve sohbet güncellemeleri bağlanmalıdır. Bu arayüz iskeleti tek başına Telegram'a giriş yapmaz.
