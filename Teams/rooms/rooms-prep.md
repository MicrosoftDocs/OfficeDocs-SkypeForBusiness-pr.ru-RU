---
title: Подготовка среды
ms.author: dstrome
author: dstrome
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b4e0ad1e-12e5-4130-aec1-d8c9cd3a5965
ms.collection:
- M365-collaboration
description: Узнайте, как подготовить инфраструктуру к развертыванию комнат Microsoft Teams, чтобы использовать все возможности.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 181599e6b5181f50548621e4895b400f442646a6
ms.sourcegitcommit: 0fddd05334e37b0086ccc0aebe17a26f8e6e8e6c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50884573"
---
# <a name="prepare-your-environment"></a><span data-ttu-id="66436-103">Подготовка среды</span><span class="sxs-lookup"><span data-stu-id="66436-103">Prepare your environment</span></span>

<span data-ttu-id="66436-104">В этом разделе приводится обзор действий, необходимых для подготовки среды к использованию всех функций комнат Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="66436-104">This section contains an overview of the steps required to prepare your environment so that you can use all of the features of Microsoft Teams Rooms.</span></span>
  
1. <span data-ttu-id="66436-105">Подготовьте учетную запись устройства для каждой консоли комнат Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="66436-105">Prepare a device account for each Microsoft Teams Rooms console.</span></span> <span data-ttu-id="66436-106">Дополнительные [сведения см. в сведениях о](rooms-deploy.md) развертывании комнат Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="66436-106">See [Deploy Microsoft Teams Rooms](rooms-deploy.md) for details.</span></span>
    
2. <span data-ttu-id="66436-107">Проверьте наличие рабочего подключения к сети или Интернету, которое будет использовать устройство. </span><span class="sxs-lookup"><span data-stu-id="66436-107">Ensure that there is a working network/Internet connection for the device to use.</span></span> 
    
   <span data-ttu-id="66436-108">Он должен иметь возможность получать IP-адрес с помощью DHCP.</span><span class="sxs-lookup"><span data-stu-id="66436-108">It must be able to receive an IP address by using DHCP.</span></span> <span data-ttu-id="66436-109">(Комнаты Microsoft Teams не могут быть настроены со статическим IP-адресом при первом запуске единицы, но затем можно настроить статический IP-адрес для устройства на устройстве, на коммутаторе или маршрутизаторе.)</span><span class="sxs-lookup"><span data-stu-id="66436-109">(Microsoft Teams Rooms cannot be configured with a static IP address at the first unit startup, but afterwards, a static IP address for the device could be configured on the device or on the upstream switch or router.)</span></span>

   <span data-ttu-id="66436-110">Они должны иметь открытые порты (в дополнение к открытию обычных портов для мультимедиа):</span><span class="sxs-lookup"><span data-stu-id="66436-110">It must have these ports open (in addition to opening the normal ports for media):</span></span>
   - <span data-ttu-id="66436-111">HTTPS: 443</span><span class="sxs-lookup"><span data-stu-id="66436-111">HTTPS: 443</span></span>
   - <span data-ttu-id="66436-112">HTTP: 80</span><span class="sxs-lookup"><span data-stu-id="66436-112">HTTP: 80</span></span>

   <span data-ttu-id="66436-113">Если в вашей сети работает прокси-сервер, вам также потребуются его адрес и данные скрипта.</span><span class="sxs-lookup"><span data-stu-id="66436-113">If your network runs through a proxy, you'll need the proxy address or script information as well.</span></span>
    
   > [!IMPORTANT]
   > <span data-ttu-id="66436-114">Комнаты Microsoft Teams не поддерживают проверку подлинности прокси-сервера, так как они могут мешать обычной работе комнаты.</span><span class="sxs-lookup"><span data-stu-id="66436-114">Microsoft Teams Rooms does not support proxy authentication as it may interfere with regular operations of the room.</span></span> <span data-ttu-id="66436-115">Перед началом производства убедитесь, что помещения Microsoft Teams исключены из проверки подлинности прокси-сервера.</span><span class="sxs-lookup"><span data-stu-id="66436-115">Ensure that Microsoft Teams Rooms have been exempted from proxy authentication before going into production.</span></span>
  
3. <span data-ttu-id="66436-116">Корпорация Майкрософт осуществляет сбор данных с целью улучшения своих продуктов.</span><span class="sxs-lookup"><span data-stu-id="66436-116">In order to improve your experience, Microsoft collects data.</span></span> <span data-ttu-id="66436-117">Чтобы разрешить корпорации Майкрософт собирать данные, разрешим эти сайты:</span><span class="sxs-lookup"><span data-stu-id="66436-117">To allow Microsoft to collect data, allow these sites:</span></span>

   - <span data-ttu-id="66436-118">Конечная точка клиента телеметрии: https://vortex.data.microsoft.com/</span><span class="sxs-lookup"><span data-stu-id="66436-118">Telemetry client endpoint: https://vortex.data.microsoft.com/</span></span>
   - <span data-ttu-id="66436-119">Конечная точка параметров телеметрии: https://settings.data.microsoft.com/</span><span class="sxs-lookup"><span data-stu-id="66436-119">Telemetry settings endpoint: https://settings.data.microsoft.com/</span></span>
    
### <a name="create-and-test-a-device-account"></a><span data-ttu-id="66436-120">Создание тестовой учетной записи устройства</span><span class="sxs-lookup"><span data-stu-id="66436-120">Create and test a device account</span></span>

<span data-ttu-id="66436-121">Учетная  *запись устройства —*  это учетная запись, которую клиент комнат Microsoft Teams использует для доступа к функциям Exchange, таким как календарь, и для того, чтобы включить Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="66436-121">A  *device account*  is an account that the Microsoft Teams Rooms client uses to access features from Exchange, like calendar, and to enable Skype for Business.</span></span> <span data-ttu-id="66436-122">Дополнительные [сведения см. в сведениях о](rooms-deploy.md) развертывании комнат Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="66436-122">See [Deploy Microsoft Teams Rooms](rooms-deploy.md) for details.</span></span>
  
### <a name="check-network-availability"></a><span data-ttu-id="66436-123">Проверка доступности сети</span><span class="sxs-lookup"><span data-stu-id="66436-123">Check network availability</span></span>

<span data-ttu-id="66436-124">Чтобы обеспечить правильную работу, устройство комнат Microsoft Teams должно иметь доступ к проводной сети, которая соответствует этим требованиям:</span><span class="sxs-lookup"><span data-stu-id="66436-124">In order to function properly, the Microsoft Teams Rooms device must have access to a wired network that meets these requirements:</span></span>
  
- <span data-ttu-id="66436-125">Доступ к экземпляру Active Directory или Azure Active Directory (Azure AD), а также серверам Microsoft Exchange и Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="66436-125">Access to your Active Directory or Azure Active Directory (Azure AD) instance, as well as your Microsoft Exchange and Skype for Business servers.</span></span>

- <span data-ttu-id="66436-126">Доступ к серверу, предоставляющему IP-адреса через DHCP.</span><span class="sxs-lookup"><span data-stu-id="66436-126">Access to a server that can provide an IP address using DHCP.</span></span> <span data-ttu-id="66436-127">Комнаты Microsoft Teams не могут быть настроены со статическим IP-адресом при первом запуске единицы.</span><span class="sxs-lookup"><span data-stu-id="66436-127">Microsoft Teams Rooms cannot be configured with a static IP address at the first unit startup.</span></span>

- <span data-ttu-id="66436-128">Доступ к HTTP-портам 80 и 443.</span><span class="sxs-lookup"><span data-stu-id="66436-128">Access to HTTP ports 80 and 443.</span></span>

- <span data-ttu-id="66436-129">Порты TCP и UDP, [](/skypeforbusiness/plan-your-deployment/network-requirements/ports-and-protocols) настроенные в требованиях к портам и протоколам для серверов для реализации локального сервера Skype для бизнеса Server, а также URL-адресов и диапазонов IP-адресов [Microsoft 365 и Office 365](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US) для решений Microsoft Teams или Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="66436-129">TCP and UDP ports configured as described in [Port and protocol requirements for servers](/skypeforbusiness/plan-your-deployment/network-requirements/ports-and-protocols) for on-premise Skype for Business Server implementations, or [Microsoft 365 and Office 365 URLs and IP address ranges](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US) for Microsoft Teams or Skype for Business online implementations.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="66436-130">Для обеспечения достаточной пропускной способности используйте проводное сетевое подключение стандарта 1 Гбит/с. </span><span class="sxs-lookup"><span data-stu-id="66436-130">Be sure to use a wired 1 Gbps network connection to assure you will have the needed bandwidth.</span></span>

> [!NOTE]
> <span data-ttu-id="66436-131">Обновления программного обеспечения для комнат Microsoft Teams автоматически загружаются из Microsoft Store для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="66436-131">Software updates for Microsoft Teams Rooms are automatically downloaded from the Microsoft Store for Business.</span></span> <span data-ttu-id="66436-132">См. [статью "Предварительные](https://docs.microsoft.com/microsoft-store/prerequisites-microsoft-store-for-business) условия для Microsoft Store для бизнеса и образования", чтобы убедиться в том, что консоль комнаты может получить доступ к магазину и для самостоятельного обновления.</span><span class="sxs-lookup"><span data-stu-id="66436-132">See [Prerequisites for Microsoft Store for Business and Education](https://docs.microsoft.com/microsoft-store/prerequisites-microsoft-store-for-business) to verify that the room console will be able to access the store and self-update.</span></span>
  
### <a name="certificates"></a><span data-ttu-id="66436-133">Сертификаты</span><span class="sxs-lookup"><span data-stu-id="66436-133">Certificates</span></span>

<span data-ttu-id="66436-134">Устройство комнат Microsoft Teams использует сертификаты для веб-служб Exchange, Microsoft Teams или Skype для бизнеса, использование сети и проверку подлинности.</span><span class="sxs-lookup"><span data-stu-id="66436-134">Your Microsoft Teams Rooms device uses certificates for Exchange Web Services, Microsoft Teams or Skype for Business, network usage, and authentication.</span></span> <span data-ttu-id="66436-135">Если связанные серверы используют открытые сертификаты (как правило, в развертываниях Online и некоторых локальных реализациях), со стороны администратора не требуется никаких дополнительных действий по установке сертификатов.</span><span class="sxs-lookup"><span data-stu-id="66436-135">If the related servers use public certificates, which is the case for Online and some On-Premises deployments, there should be no further action required on the part of the admin to install certificates.</span></span> <span data-ttu-id="66436-136">Если используется закрытый центр сертификации (как правило, в локальных развертываниях), на устройстве необходимо настроить доверие такому ЦС, то есть установить на нем сертификаты ЦС и цепочки ЦС.</span><span class="sxs-lookup"><span data-stu-id="66436-136">If, on the other hand, the certificate authority is a private CA (typical for On-Premises deployments) then the device needs to trust that CA which means having the CA + CA chain certificates installed on the device.</span></span> <span data-ttu-id="66436-137">При добавлении устройства в домен эта задача может быть выполнена автоматически.</span><span class="sxs-lookup"><span data-stu-id="66436-137">Adding the device to the domain may perform this task automatically.</span></span>
  
<span data-ttu-id="66436-138">Сертификаты устанавливаются так же, как для любого другого клиента Windows. </span><span class="sxs-lookup"><span data-stu-id="66436-138">You will install certificates the same way you would for any other Windows client.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="66436-139">Чтобы комнаты Microsoft Teams могли использовать Skype для бизнеса Server, могут потребоваться сертификаты.</span><span class="sxs-lookup"><span data-stu-id="66436-139">Certificates may be required in order to have Microsoft Teams Rooms use Skype for Business Server.</span></span>
  
### <a name="proxy"></a><span data-ttu-id="66436-140">Прокси-сервер</span><span class="sxs-lookup"><span data-stu-id="66436-140">Proxy</span></span>

<span data-ttu-id="66436-141">Комнаты Microsoft Teams предназначены для наследования параметров прокси-сервера от ос Windows.</span><span class="sxs-lookup"><span data-stu-id="66436-141">Microsoft Teams Rooms is designed to inherit Proxy settings from the Windows OS.</span></span> <span data-ttu-id="66436-142">Для доступа к параметрам ОС Windows выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="66436-142">Access the Windows OS in the following manner:</span></span>
  
1. <span data-ttu-id="66436-143">В пользовательском интерфейсе комнат Microsoft Teams щелкните значок шестеренки "Параметры", где вам будет предложено вводить пароль локального администратора на устройстве (пароль по умолчанию **— SFB).**</span><span class="sxs-lookup"><span data-stu-id="66436-143">In the Microsoft Teams Rooms UI, click on the Settings gear icon where you'll be prompted for the local Administrator password on the device (the default password is **sfb**).</span></span>
2. <span data-ttu-id="66436-144">Коснитесь параметров, а затем нажмите кнопку "Перейти в **Windows",** а  затем коснитесь кнопки "Перейти к входу администратора", а затем нажмите кнопку "Администратор" (если компьютер присоединился к домену, выберите "Другой  пользователь", а затем в качестве имени пользователя выберите ".\admin").  </span><span class="sxs-lookup"><span data-stu-id="66436-144">Tap on **Settings** followed by tapping on the **Go to Windows** button and then tapping on the **go to Admin Sign In** button and then clicking the **Administrator** button (if the computer is domain joined choose **Other User,** then use .\admin as the user name).</span></span>
3. <span data-ttu-id="66436-145">В поле **поиска Windows** слева внизу введите regedit (длинное нажатие экрана или щелкните правой кнопкой мыши и выберите "Запуск **от администратора").**</span><span class="sxs-lookup"><span data-stu-id="66436-145">In the **Search Windows** box bottom left type in regedit (either long press the screen or right click and choose **Run as administrator**).</span></span>
4. <span data-ttu-id="66436-146">Щелкните папку HKEY_USERS (вы увидите список идентификаторов SID пользователей компьютера) и убедитесь в том, что выбрана корневая папка HKEY_USERS.</span><span class="sxs-lookup"><span data-stu-id="66436-146">Click on the HKEY_USERS folder (you'll see a list of machine user SIDs) ensure the root folder HKEY_USERS is selected.</span></span>
       
5. <span data-ttu-id="66436-147">Щелкните "Файл" и выберите **"Загрузитьгрузку".**</span><span class="sxs-lookup"><span data-stu-id="66436-147">Click on File and then choose **Load Hive.**</span></span>
6. <span data-ttu-id="66436-148">Перейдите в **папку C:\Users\Skype** и введите в поле "Имя файла" N ПЕРЕЯДОТКА.dat и нажмите кнопку "Открыть"</span><span class="sxs-lookup"><span data-stu-id="66436-148">Browse to the **C:\Users\Skype** folder and type in the File name box NTUSER.dat and press the open button</span></span>

7. <span data-ttu-id="66436-149">Вам будет предложено в качестве имени ключа для загруженного ключа. введите в Skype (теперь вы увидите параметры реестра для пользователя Skype).</span><span class="sxs-lookup"><span data-stu-id="66436-149">You'll be prompted for a Key Name for your newly loaded Hive; type in Skype (you should now see the registry settings for the Skype User).</span></span>
 
8. <span data-ttu-id="66436-150">Откройте клавишу Skype и перейдите к HKEY_USERS\Skype\SOFTWARE\Microsoft\Windows\CurrentVersion\Internet Settings ввели эти параметры:</span><span class="sxs-lookup"><span data-stu-id="66436-150">Open the Skype key and browse to HKEY_USERS\Skype\SOFTWARE\Microsoft\Windows\CurrentVersion\Internet Settings then ensure these settings are entered:</span></span> 
    
    ```console
    [HKEY_USERS\Skype\SOFTWARE\Microsoft\Windows\CurrentVersion\Internet Settings]
    "MigrateProxy"=dword:00000001
    "ProxyEnable"=dword:00000001
    "ProxyServer"="xx.xx.xx.xx:8080"
    ```
    
    <span data-ttu-id="66436-151">Если параметр ProxyServer не существует, его может потребоваться добавить в качестве строкового параметра. Замените xx.xx.xx.xx:8080 на IP-адрес или имя узла и порт вашего прокси-сервера.</span><span class="sxs-lookup"><span data-stu-id="66436-151">If ProxyServer doesn't exist you may have to add this key as a string, change the xx.xx.xx.xx:8080 to the ip/host and port of your Proxy server.</span></span>
 
    <span data-ttu-id="66436-152">Если клиент использует PAC-файл, конфигурация будет выглядеть так:</span><span class="sxs-lookup"><span data-stu-id="66436-152">If the customer is using a PAC file the configuration would look like the example below:</span></span>

     ```console
    [HKEY_USERS\Skype\SOFTWARE\Microsoft\Windows\CurrentVersion\Internet Settings]
    "MigrateProxy"=dword:00000001
    "ProxyEnable"=dword:00000001
    "AutoConfigURL"=http://contosoproxy.corp.net/proxy.pac
    ```
    
9. <span data-ttu-id="66436-153">Завершив внесение изменений, выделите раздел Skype User (корневую папку Skype), а затем в меню "Файл" редактора реестра выберите пункт "Выгрузить куст" (появится запрос на подтверждение — выберите **Да**).</span><span class="sxs-lookup"><span data-stu-id="66436-153">Once you are finished making your changes highlight the Skype User key (root folder for Skype) and choose unload Hive from the Registry file menu (you'll be prompted for confirmation - select **Yes**).</span></span>
    
10. <span data-ttu-id="66436-154">Теперь можно закрыть редактор реестра и ввести logoff в поле "Поиск в Windows".</span><span class="sxs-lookup"><span data-stu-id="66436-154">You can now close the registry editor and type logoff into the Windows search box.</span></span>
    
11. <span data-ttu-id="66436-155">Вернувшись на экран входа, выберите пользователя **Skype**.</span><span class="sxs-lookup"><span data-stu-id="66436-155">Back at the sign-in screen, choose the **Skype** user.</span></span> <span data-ttu-id="66436-156">Если все предыдущие шаги были успешными, вход будет успешно завершен на устройстве с комнатами Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="66436-156">If all the previous steps were successful, the Microsoft Teams Rooms device will sign-in successfully.</span></span>
    
<span data-ttu-id="66436-157">Подробные [сведения о полных](https://docs.microsoft.com/microsoftteams/rooms/security#network-security) полных и полных номерах полных номеров, портах и диапазонах IP-адресов, необходимых для комнат Microsoft Teams, см. в статье "Безопасность сети".</span><span class="sxs-lookup"><span data-stu-id="66436-157">See the [Network Security](https://docs.microsoft.com/microsoftteams/rooms/security#network-security) article for full details on FQDNs, ports, and IP address ranges required for Microsoft Teams Rooms.</span></span>
  
  
### <a name="create-provisioning-packages"></a><span data-ttu-id="66436-158">Создание пакетов подготовки</span><span class="sxs-lookup"><span data-stu-id="66436-158">Create provisioning packages</span></span>

<span data-ttu-id="66436-159">Пакеты подготовка будут применяться для проверки подлинности Exchange Server, Microsoft 365 или Office 365.</span><span class="sxs-lookup"><span data-stu-id="66436-159">You will use provisioning packages to authenticate to Exchange Server, Microsoft 365, or Office 365.</span></span>
  
### <a name="admin-group-management"></a><span data-ttu-id="66436-160">Управление группой администраторов</span><span class="sxs-lookup"><span data-stu-id="66436-160">Admin group management</span></span>

<span data-ttu-id="66436-161">После присоединения к домену вы можете настроить группу безопасности в качестве локального администратора с помощью групповой политики или оснастки управления локальным компьютером так же, как для компьютера с ОС Windows в своем домене.</span><span class="sxs-lookup"><span data-stu-id="66436-161">After domain joining, you can use Group Policy or the Local Computer Management to set a Security Group as local administrator just like you would for a Windows PC in your domain.</span></span> <span data-ttu-id="66436-162">Любой участник этой группы безопасности сможет ввести свои учетные данные и разблокировать раздел "Параметры".</span><span class="sxs-lookup"><span data-stu-id="66436-162">Anyone who is a member of that security group can enter their credentials and unlock Settings.</span></span>
  
> [!NOTE]
> <span data-ttu-id="66436-163">Если ваше устройство с приложением "Комнаты Microsoft Teams" утрачивает отношение доверия с доменом (например, если вы удалите "Комнаты Microsoft Teams" из домена после присоединения к нему), вы не сможете пройти проверку подлинности на устройстве и открыть раздел "Параметры".</span><span class="sxs-lookup"><span data-stu-id="66436-163">If your Microsoft Teams Rooms device loses trust with the domain (for example, if you remove the Microsoft Teams Rooms from the domain after it is domain joined), you won't be able to authenticate into the device and open up Settings.</span></span> <span data-ttu-id="66436-164">В качестве обходного решения войдите с помощью локальной учетной записи администратора.</span><span class="sxs-lookup"><span data-stu-id="66436-164">The workaround is to log in with the local Admin account.</span></span> 
  
## <a name="local-accounts"></a><span data-ttu-id="66436-165">Локальные учетные записи</span><span class="sxs-lookup"><span data-stu-id="66436-165">Local accounts</span></span>

### <a name="microsoft-teams-rooms-local-user-account"></a><span data-ttu-id="66436-166">Учетная запись локального пользователя Комнаты Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="66436-166">Microsoft Teams Rooms Local User Account</span></span>

<span data-ttu-id="66436-167">Учетная запись устройства, как правило, не использует пароль.</span><span class="sxs-lookup"><span data-stu-id="66436-167">The Device Account does not typically use a password.</span></span> <span data-ttu-id="66436-168">При необходимости ей можно назначить пароль, однако это может иметь негативные последствия, включая вероятность блокировки консольного приложения при истечении срока действия пароля.</span><span class="sxs-lookup"><span data-stu-id="66436-168">It is possible to give it a password, but there are consequences, including a possibility that users might get locked out of the console application when that password expires.</span></span> <span data-ttu-id="66436-169">Соответственно, администратор должен установить настройки таким образом, чтобы срок действия пароля не истекал.</span><span class="sxs-lookup"><span data-stu-id="66436-169">Consequently, the administrator should take are to ensure that the password is not allowed to expire.</span></span>
  
### <a name="admin---local-administrator-account"></a><span data-ttu-id="66436-170">Admin — учетная запись локального администратора</span><span class="sxs-lookup"><span data-stu-id="66436-170">"Admin" - Local Administrator Account</span></span>

<span data-ttu-id="66436-171">Для комнат Microsoft Teams по умолчанию установлен пароль "sfb".</span><span class="sxs-lookup"><span data-stu-id="66436-171">Microsoft Teams Rooms default password is set to "sfb".</span></span> <span data-ttu-id="66436-172">Пароль можно изменить локально, перейдите в параметры Windows перейти в Windows или в файл AutoUnattend.xml (внести изменения в XML-файл можно с помощью диспетчера изображений Системы Windows из \> ADK).</span><span class="sxs-lookup"><span data-stu-id="66436-172">The Password can be changed locally by going to Windows Settings \> Go to Windows or in the AutoUnattend.xml file (use the Windows System Image manager from ADK to make the change to the xml file).</span></span>
  
> [!CAUTION]
> <span data-ttu-id="66436-173">Обязательно измените пароль комнат Microsoft Teams как можно скорее.</span><span class="sxs-lookup"><span data-stu-id="66436-173">Be sure to change the Microsoft Teams Rooms password as soon as possible.</span></span> 
  
<span data-ttu-id="66436-174">Кроме того, для управления паролем локального администратора можно настроить групповую политику, в которой администраторы домена получают права локальных администраторов.</span><span class="sxs-lookup"><span data-stu-id="66436-174">You can also manage the Local Administrator password by setting up a group policy where domain admins are made local admins.</span></span>
  
<span data-ttu-id="66436-175">Пароль локального администратора нельзя выбрать во время настройки.</span><span class="sxs-lookup"><span data-stu-id="66436-175">The Local admin password is not included as a choice during Setup.</span></span>
  
### <a name="machine-account"></a><span data-ttu-id="66436-176">Учетная запись компьютера</span><span class="sxs-lookup"><span data-stu-id="66436-176">Machine Account</span></span>

<span data-ttu-id="66436-177">Как и любое устройство с Windows, имя компьютера можно  переименовать, щелкнув правой кнопкой мыши в окне "Параметры о \>  \> **переименовании компьютера".**</span><span class="sxs-lookup"><span data-stu-id="66436-177">Much like any Windows device, the Machine Name can be renamed by right-clicking in **Settings** \> **About** \> **Rename PC**.</span></span>
  
<span data-ttu-id="66436-178">Если вы хотите переименовать компьютер после его присоединения к домену, воспользуйтесь командой PowerShell "Переименовать **компьютер",** а затем — новым именем компьютера.</span><span class="sxs-lookup"><span data-stu-id="66436-178">If you would like to rename the computer after joining it to a domain, use **Rename-Computer**, a PowerShell command, followed by the computer's new name.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="66436-179">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="66436-179">Related topics</span></span>

[<span data-ttu-id="66436-180">Планирование комнат Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="66436-180">Plan Microsoft Teams Rooms</span></span>](rooms-plan.md)

[<span data-ttu-id="66436-181">Требования к комнатам Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="66436-181">Microsoft Teams Rooms requirements</span></span>](requirements.md)
  
[<span data-ttu-id="66436-182">Развертывание комнат Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="66436-182">Deploy Microsoft Teams Rooms</span></span>](rooms-deploy.md)
  
[<span data-ttu-id="66436-183">Настройка консоли комнат Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="66436-183">Configure a Microsoft Teams Rooms console</span></span>](console.md)
  
[<span data-ttu-id="66436-184">Управление комнатами Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="66436-184">Manage Microsoft Teams Rooms</span></span>](rooms-manage.md)

[<span data-ttu-id="66436-185">Необходимые условия для Microsoft Store для бизнеса и образования</span><span class="sxs-lookup"><span data-stu-id="66436-185">Prerequisites for Microsoft Store for Business and Education</span></span>](https://docs.microsoft.com/microsoft-store/prerequisites-microsoft-store-for-business) 
