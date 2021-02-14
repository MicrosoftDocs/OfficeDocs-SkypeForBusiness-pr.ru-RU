---
title: Настройка двух коэффициентов проверки подлинности в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: c24e0891-e108-4cb6-9902-c6a4c8e68455
description: Сводка. Настройка двух коэффициентов проверки подлинности в Skype для бизнеса Server.
ms.openlocfilehash: a7c5b4489b6b39e924a85c5e99796044d892c11f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814419"
---
# <a name="configure-two-factor-authentication-in-skype-for-business-server"></a><span data-ttu-id="b4e3b-103">Настройка двух коэффициентов проверки подлинности в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="b4e3b-103">Configure two-factor authentication in Skype for Business Server</span></span>

<span data-ttu-id="b4e3b-104">**Сводка:** Настройка двух коэффициентов проверки подлинности в Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="b4e3b-104">**Summary:** Configure two-factor authentication in Skype for Business Server.</span></span>

<span data-ttu-id="b4e3b-105">В следующих разделах описаны действия, необходимые для настройки двух коэффициентов проверки подлинности для развертывания.</span><span class="sxs-lookup"><span data-stu-id="b4e3b-105">The following sections describe the steps necessary to configure two-factor authentication for your deployment.</span></span> <span data-ttu-id="b4e3b-106">Дополнительные сведения о двухфакторной проверке подлинности см. в подсистеме "Включение многофакторной проверки подлинности Office 365 для администраторов в [Интернете" "Публикация пользователя сетки".](https://go.microsoft.com/fwlink/p/?LinkId=313332)</span><span class="sxs-lookup"><span data-stu-id="b4e3b-106">For more information about Two-factor authentication, see [Enabling Office 365 multi-factor authentication for online administrators - Grid User Post](https://go.microsoft.com/fwlink/p/?LinkId=313332).</span></span>

## <a name="configure-an-enterprise-root-certificate-authority-to-support-smart-card-authentication"></a><span data-ttu-id="b4e3b-107">Настройка корпоративного корневого сертификата для поддержки проверки подлинности смарт-карт</span><span class="sxs-lookup"><span data-stu-id="b4e3b-107">Configure an Enterprise Root Certificate Authority to Support Smart Card Authentication</span></span>

<span data-ttu-id="b4e3b-108">Ниже описано, как настроить корпоративный корневой ЦС для поддержки проверки подлинности смарт-карт.</span><span class="sxs-lookup"><span data-stu-id="b4e3b-108">The following steps describe how to configure an Enterprise Root CA to support Smart Card Authentication:</span></span>

<span data-ttu-id="b4e3b-109">Сведения об установке корпоративного корневого ЦС см. в процедуре [установки корпоративного корневого ЦС.](https://go.microsoft.com/fwlink/p/?LinkID=313364)</span><span class="sxs-lookup"><span data-stu-id="b4e3b-109">For information on how to install an Enterprise Root CA, see [Install an Enterprise Root Certification Authority](https://go.microsoft.com/fwlink/p/?LinkID=313364).</span></span>

1. <span data-ttu-id="b4e3b-110">Войдите на компьютер корпоративного ЦС с помощью учетной записи администратора домена.</span><span class="sxs-lookup"><span data-stu-id="b4e3b-110">Log in to the Enterprise CA computer using a Domain Admin account.</span></span>

2. <span data-ttu-id="b4e3b-111">Запустите system Manager и убедитесь, что установлена роль веб-регистрации в службе сертификации.</span><span class="sxs-lookup"><span data-stu-id="b4e3b-111">Launch System Manager, and verify that the Certificate Authority Web Enrollment role is installed.</span></span>

3. <span data-ttu-id="b4e3b-112">В меню **"Администрирование"** откройте консоль управления **"Сертификация".**</span><span class="sxs-lookup"><span data-stu-id="b4e3b-112">From the **Administrative Tools** menu, open the **Certification Authority** management console.</span></span>

4. <span data-ttu-id="b4e3b-113">В области навигации разо **расширении сертификации.**</span><span class="sxs-lookup"><span data-stu-id="b4e3b-113">In the Navigation pane, expand **Certification Authority**.</span></span>

5. <span data-ttu-id="b4e3b-114">Щелкните правой кнопкой мыши **шаблоны сертификатов,** выберите **"Новый"** и выберите **"Шаблон сертификата для выдачи".**</span><span class="sxs-lookup"><span data-stu-id="b4e3b-114">Right click on **Certificate Templates**, select **New**, then select **Certificate Template to Issue**.</span></span>

6. <span data-ttu-id="b4e3b-115">Выберите **агент регистрации,** **пользователь смарт-карты** и **учетные данные смарт-карты.**</span><span class="sxs-lookup"><span data-stu-id="b4e3b-115">Select **Enrollment Agent**, **Smartcard User**, and **Smartcard Logon**.</span></span>

7. <span data-ttu-id="b4e3b-116">Нажмите **ОК**.</span><span class="sxs-lookup"><span data-stu-id="b4e3b-116">Click **OK**.</span></span>

8. <span data-ttu-id="b4e3b-117">Щелкните правой **кнопкой мыши шаблоны сертификатов.**</span><span class="sxs-lookup"><span data-stu-id="b4e3b-117">Right click on **Certificate Templates**.</span></span>

9. <span data-ttu-id="b4e3b-118">Выберите **"Управление".**</span><span class="sxs-lookup"><span data-stu-id="b4e3b-118">Select **Manage**.</span></span>

10. <span data-ttu-id="b4e3b-119">Откройте свойства шаблона "Пользователь смарт-карты".</span><span class="sxs-lookup"><span data-stu-id="b4e3b-119">Open the properties of the Smartcard User template.</span></span>

11. <span data-ttu-id="b4e3b-120">Щелкните **вкладку "Безопасность".**</span><span class="sxs-lookup"><span data-stu-id="b4e3b-120">Click on the **Security** tab.</span></span>

12. <span data-ttu-id="b4e3b-121">Измените разрешения следующим образом:</span><span class="sxs-lookup"><span data-stu-id="b4e3b-121">Change the permissions as follows:</span></span>

    - <span data-ttu-id="b4e3b-122">Добавление учетных записей AD отдельных пользователей с разрешениями на чтение и регистрацию (разрешение) или</span><span class="sxs-lookup"><span data-stu-id="b4e3b-122">Add individual user AD accounts with Read/Enroll (Allow) permissions, or</span></span>

    - <span data-ttu-id="b4e3b-123">Добавление группы безопасности, содержащей пользователей смарт-карт с разрешениями на чтение и регистрацию (разрешение) или</span><span class="sxs-lookup"><span data-stu-id="b4e3b-123">Add a security group containing smart card users with Read/Enroll (Allow) permissions, or</span></span>

    - <span data-ttu-id="b4e3b-124">Добавление группы "Пользователи домена" с разрешениями на чтение и регистрацию (разрешение)</span><span class="sxs-lookup"><span data-stu-id="b4e3b-124">Add the Domain Users group with Read/Enroll (Allow) permissions</span></span>

## <a name="configure-windows-8-for-virtual-smart-cards"></a><span data-ttu-id="b4e3b-125">Настройка Windows 8 виртуальных смарт-карт</span><span class="sxs-lookup"><span data-stu-id="b4e3b-125">Configure Windows 8 for Virtual Smart Cards</span></span>

<span data-ttu-id="b4e3b-126">Одним из факторов, которые следует учитывать при развертывании двух коэффициентов проверки подлинности и технологии смарт-карт, является стоимость реализации.</span><span class="sxs-lookup"><span data-stu-id="b4e3b-126">One factor to consider when deploying two-factor authentication and smart card technology is the cost of implementation.</span></span> <span data-ttu-id="b4e3b-127">Windows 8 предоставляет ряд новых возможностей безопасности, а одной из наиболее интересных новых функций является поддержка виртуальных смарт-карт.</span><span class="sxs-lookup"><span data-stu-id="b4e3b-127">Windows 8 provides a number of new security capabilities, and one of the most interesting new features is support for virtual smart cards.</span></span>

<span data-ttu-id="b4e3b-128">Для компьютеров, оснащенных микросхемой доверенного платформенного модуля (TPM), которая соответствует спецификации версии 1.2, организации теперь могут получить преимущества для работы с смарт-картами без каких-либо дополнительных инвестиций в оборудование.</span><span class="sxs-lookup"><span data-stu-id="b4e3b-128">For computers equipped with a Trusted Platform Module (TPM) chip that meets specification version 1.2, organizations can now get the benefits of smart card logon without making any additional investments in hardware.</span></span> <span data-ttu-id="b4e3b-129">Дополнительные сведения см. в [теме "Использование виртуальных смарт-карт с Windows 8.](https://go.microsoft.com/fwlink/p/?LinkId=313365)</span><span class="sxs-lookup"><span data-stu-id="b4e3b-129">For more information, see [Using Virtual Smart Cards with Windows 8](https://go.microsoft.com/fwlink/p/?LinkId=313365).</span></span>

### <a name="to-configure-windows-8-for-virtual-smart-cards"></a><span data-ttu-id="b4e3b-130">Настройка Windows 8 виртуальных смарт-карт</span><span class="sxs-lookup"><span data-stu-id="b4e3b-130">To Configure Windows 8 for Virtual Smart Cards</span></span>

1. <span data-ttu-id="b4e3b-131">Войдите на Windows 8, используя учетные данные пользователя, включенного в Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="b4e3b-131">Log in to the Windows 8 computer using the credentials of a Skype for Business-enabled user.</span></span>

2. <span data-ttu-id="b4e3b-132">На Windows 8 экрана переместите курсор в нижний правый угол экрана.</span><span class="sxs-lookup"><span data-stu-id="b4e3b-132">At the Windows 8 Start screen, move your cursor to the bottom right corner of the screen.</span></span>

3. <span data-ttu-id="b4e3b-133">Выберите параметр **"Поиск",** а затем наберите "Command Prompt".</span><span class="sxs-lookup"><span data-stu-id="b4e3b-133">Select the **Search** option, and then search forCommand Prompt.</span></span>

4. <span data-ttu-id="b4e3b-134">Щелкните правой **кнопкой** мыши командную подсказку и выберите команду **"Запуск от прав администратора".**</span><span class="sxs-lookup"><span data-stu-id="b4e3b-134">Right click on **Command Prompt**, and then select **Run as Administrator**.</span></span>

5. <span data-ttu-id="b4e3b-135">Откройте консоль управления доверенным платформенного модуля (TPM) с помощью следующей команды:</span><span class="sxs-lookup"><span data-stu-id="b4e3b-135">Open the Trusted Platform Module (TPM) Management console by running the following command:</span></span>

  ```console
  Tpm.msc
  ```

6. <span data-ttu-id="b4e3b-136">В консоли управления TPM убедитесь, что версия спецификации TPM не менее 1.2</span><span class="sxs-lookup"><span data-stu-id="b4e3b-136">From the TPM management console, verify that your TPM specification version is at least 1.2</span></span>

    > [!NOTE]
    > <span data-ttu-id="b4e3b-137">Если вы получаете диалоговое окно с указанием того, что совместимый модуль платформы доверия (TPM) не найден, убедитесь, что на компьютере есть совместимый модуль TPM и что он включен в BIOS системы.</span><span class="sxs-lookup"><span data-stu-id="b4e3b-137">If you receive a dialog stating that a Compatible Trust Platform Module (TPM) cannot be found, verify that the computer has a compatible TPM module and that it is enabled in the system BIOS.</span></span>

7. <span data-ttu-id="b4e3b-138">Закройте консоль управления TPM</span><span class="sxs-lookup"><span data-stu-id="b4e3b-138">Close the TPM management console</span></span>

8. <span data-ttu-id="b4e3b-139">Создайте виртуальную смарт-карту в командной области с помощью следующей команды:</span><span class="sxs-lookup"><span data-stu-id="b4e3b-139">From the command prompt, create a new virtual smart card using the following command:</span></span>

  ```console
  TpmVscMgr create /name MyVSC /pin default /adminkey random /generate
  ```

    > [!NOTE]
    > <span data-ttu-id="b4e3b-140">Чтобы предоставить пользовательское значение ПИН-кода при создании виртуальной смарт-карты, используйте /pin-запрос.</span><span class="sxs-lookup"><span data-stu-id="b4e3b-140">To provide a custom PIN value when creating the virtual smart card, use /pin prompt instead.</span></span>

9. <span data-ttu-id="b4e3b-141">Откройте консоль управления компьютером в командной командной консоли, выляв следующую команду:</span><span class="sxs-lookup"><span data-stu-id="b4e3b-141">From the command prompt, open the Computer Management console by running the following command:</span></span>

  ```console
  CompMgmt.msc
  ```

10. <span data-ttu-id="b4e3b-142">В консоли "Управление компьютером" выберите **"Управление устройствами".**</span><span class="sxs-lookup"><span data-stu-id="b4e3b-142">In the Computer Management console, select **Device Management**.</span></span>

11. <span data-ttu-id="b4e3b-143">Развернуть **считыватели смарт-карт.**</span><span class="sxs-lookup"><span data-stu-id="b4e3b-143">Expand **Smart card readers**.</span></span>

12. <span data-ttu-id="b4e3b-144">Убедитесь, что новое устройство чтения виртуальных смарт-карт успешно создано.</span><span class="sxs-lookup"><span data-stu-id="b4e3b-144">Verify that the new virtual smart card reader has been created successfully.</span></span>

## <a name="enroll-users-for-smart-card-authentication"></a><span data-ttu-id="b4e3b-145">Регистрация пользователей для проверки подлинности с смарт-картой</span><span class="sxs-lookup"><span data-stu-id="b4e3b-145">Enroll users for smart card authentication</span></span>

<span data-ttu-id="b4e3b-146">Обычно существует два способа регистрации пользователей для проверки подлинности с смарт-картой.</span><span class="sxs-lookup"><span data-stu-id="b4e3b-146">There are generally two methods for enrolling users for smart card authentication.</span></span> <span data-ttu-id="b4e3b-147">Более простой способ состоит в непосредственной регистрации пользователей для проверки подлинности с помощью смарт-карты с помощью веб-регистрации, в то время как более сложный метод подразумевает использование агента регистрации.</span><span class="sxs-lookup"><span data-stu-id="b4e3b-147">The easier method involves having users enroll directly for smart card authentication using web enrollment, while the more complex method involves using an enrollment agent.</span></span> <span data-ttu-id="b4e3b-148">В этом разделе основное внимание уделяется самостоятельной регистрации сертификатов смарт-карт.</span><span class="sxs-lookup"><span data-stu-id="b4e3b-148">This topic focuses on self-enrollment for smartcard certificates.</span></span>

<span data-ttu-id="b4e3b-149">Дополнительные сведения о регистрации от имени пользователей в качестве агента регистрации см. в подсети "Регистрация сертификатов от имени [других пользователей".](https://go.microsoft.com/fwlink/p/?LinkID=313367)</span><span class="sxs-lookup"><span data-stu-id="b4e3b-149">For more information on enrolling on behalf of users as an enrollment agent, see [Enroll for Certificates on Behalf of Other Users](https://go.microsoft.com/fwlink/p/?LinkID=313367).</span></span>

### <a name="to-enroll-users-for-smart-card-authentication"></a><span data-ttu-id="b4e3b-150">Регистрация пользователей для проверки подлинности смарт-карт</span><span class="sxs-lookup"><span data-stu-id="b4e3b-150">To Enroll Users for Smart Card Authentication</span></span>

1. <span data-ttu-id="b4e3b-151">Войдите на Windows 8, используя учетные данные пользователя, включенного в Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="b4e3b-151">Log in to the Windows 8 workstation using the credentials of a Skype for Business-enabled user.</span></span>

2. <span data-ttu-id="b4e3b-152">Запустите Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="b4e3b-152">Launch Internet Explorer.</span></span>

3. <span data-ttu-id="b4e3b-153">Перейдите на **страницу веб-регистрации в** службе сертификации (например, https://MyCA.contoso.com/certsrv)</span><span class="sxs-lookup"><span data-stu-id="b4e3b-153">Browse to the **Certificate Authority Web Enrollment** page (e.g. https://MyCA.contoso.com/certsrv).</span></span>

    > [!NOTE]
    > <span data-ttu-id="b4e3b-154">Если вы используете Internet Explorer 10, может потребоваться просмотреть этот веб-сайт в режиме совместимости.</span><span class="sxs-lookup"><span data-stu-id="b4e3b-154">If you are using Internet Explorer 10, you may need to view this website in Compatibility Mode.</span></span>

4. <span data-ttu-id="b4e3b-155">На странице **приветствия** выберите запрос **сертификата.**</span><span class="sxs-lookup"><span data-stu-id="b4e3b-155">On the **Welcome** Page, select **Request a certificate**.</span></span>

5. <span data-ttu-id="b4e3b-156">Затем выберите **"Расширенный запрос".**</span><span class="sxs-lookup"><span data-stu-id="b4e3b-156">Next, select **Advanced Request**.</span></span>

6. <span data-ttu-id="b4e3b-157">Выберите **"Создать" и отправьте запрос в этот ЦС.**</span><span class="sxs-lookup"><span data-stu-id="b4e3b-157">Select **Create and submit a request to this CA**.</span></span>

7. <span data-ttu-id="b4e3b-158">Выберите **"Пользователь смарт-карты"** в разделе **"Шаблон** сертификата" и выполните расширенный запрос сертификата со следующими значениями:</span><span class="sxs-lookup"><span data-stu-id="b4e3b-158">Select **Smartcard User** under the **Certificate Template** section and complete the advanced certificate request with the following values:</span></span>

  - <span data-ttu-id="b4e3b-159">**Ключевые параметры** подтверждают, что он:</span><span class="sxs-lookup"><span data-stu-id="b4e3b-159">**Key Options** confirm he following settings:</span></span>

    - <span data-ttu-id="b4e3b-160">Select the **Create new key set** radio button</span><span class="sxs-lookup"><span data-stu-id="b4e3b-160">Select the **Create new key set** radio button</span></span>

    - <span data-ttu-id="b4e3b-161">Для **CSP выберите** **microsoft Base Smart Card Crypto Provider**</span><span class="sxs-lookup"><span data-stu-id="b4e3b-161">For **CSP**, select **Microsoft Base Smart Card Crypto Provider**</span></span>

    - <span data-ttu-id="b4e3b-162">Для **использования ключей** выберите **Exchange** (это единственный доступный вариант).</span><span class="sxs-lookup"><span data-stu-id="b4e3b-162">For **Key Usage**, select **Exchange** (this is the only option available).</span></span>

    - <span data-ttu-id="b4e3b-163">For **Key Size**, enter 2048</span><span class="sxs-lookup"><span data-stu-id="b4e3b-163">For **Key Size**, enter 2048</span></span>

    - <span data-ttu-id="b4e3b-164">Подтверждение выбора **имени контейнера автоматического** ключа</span><span class="sxs-lookup"><span data-stu-id="b4e3b-164">Confirm that **Automatic key container name** is selected</span></span>

    - <span data-ttu-id="b4e3b-165">Оставьте остальные флажки без флажков.</span><span class="sxs-lookup"><span data-stu-id="b4e3b-165">Leave the other boxes unchecked.</span></span>

  - <span data-ttu-id="b4e3b-166">В **области дополнительных параметров** подтвердим следующие значения:</span><span class="sxs-lookup"><span data-stu-id="b4e3b-166">Under **Additional Options** confirm the following values:</span></span>

    - <span data-ttu-id="b4e3b-167">Для **формата запроса** выберите **CMC**.</span><span class="sxs-lookup"><span data-stu-id="b4e3b-167">For **Request Format** select **CMC**.</span></span>

    - <span data-ttu-id="b4e3b-168">Для **алгоритма hash select** **sha1**.</span><span class="sxs-lookup"><span data-stu-id="b4e3b-168">For **Hash Algorithm** select **sha1**.</span></span>

    - <span data-ttu-id="b4e3b-169">Для **friendly Name** enterSmardcard Certificate.</span><span class="sxs-lookup"><span data-stu-id="b4e3b-169">For **Friendly Name** enterSmardcard Certificate.</span></span>

8. <span data-ttu-id="b4e3b-170">Если вы используете физическое устройство чтения смарт-карт, вставьте смарт-карту в устройство.</span><span class="sxs-lookup"><span data-stu-id="b4e3b-170">If you are using a physical smartcard reader, insert the smart card into the device.</span></span>

9. <span data-ttu-id="b4e3b-171">Нажмите **кнопку** "Отправить", чтобы отправить запрос на сертификат.</span><span class="sxs-lookup"><span data-stu-id="b4e3b-171">Click **Submit** to submit the certificate request.</span></span>

10. <span data-ttu-id="b4e3b-172">При запросе введите ПИН-код, который использовался для создания виртуальной смарт-карты.</span><span class="sxs-lookup"><span data-stu-id="b4e3b-172">When prompted, enter the PIN that was used to create the virtual smart card.</span></span>

    > [!NOTE]
    > <span data-ttu-id="b4e3b-173">Значение ПИН-кода виртуальной смарт-карты по умолчанию — "12345678".</span><span class="sxs-lookup"><span data-stu-id="b4e3b-173">The default virtual smart card PIN value is '12345678'.</span></span>

11. <span data-ttu-id="b4e3b-174">После выдачи сертификата нажмите кнопку **"Установить этот сертификат",** чтобы завершить процесс регистрации.</span><span class="sxs-lookup"><span data-stu-id="b4e3b-174">Once the certificate has been issued, click **Install this certificate** to complete the enrollment process.</span></span>

    > [!NOTE]
    >  <span data-ttu-id="b4e3b-175">Если запрос сертификата не удается с ошибкой "Этот веб-браузер не поддерживает генерацию запросов сертификатов", существует три возможных способа решения проблемы:</span><span class="sxs-lookup"><span data-stu-id="b4e3b-175">If your certificate request fails with the error "This Web browser does not support the generation of certificate requests," there are three possible ways to resolve the issue:</span></span>

        a. Enable Compatibility View in Internet Explorer
        b. Enable the Turn on Intranet settings option in Internet Explorer
        c. Select the Reset all zones to default level setting under the Security tab in the Internet Explorer options menu.

## <a name="configure-active-directory-federation-services-ad-fs-20"></a><span data-ttu-id="b4e3b-176">Настройка служб федерации Active Directory (AD FS 2.0)</span><span class="sxs-lookup"><span data-stu-id="b4e3b-176">Configure Active Directory Federation Services (AD FS 2.0)</span></span>

<span data-ttu-id="b4e3b-177">В следующем разделе описывается настройка служб федерации Active Directory (AD FS 2.0) для поддержки многофакторной проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="b4e3b-177">The following section describes how to configure Active Directory Federation Services (AD FS 2.0) to support multi-factor authentication.</span></span> <span data-ttu-id="b4e3b-178">Сведения об установке AD FS 2.0 см. в пошаговом руководстве по [AD FS 2.0.](https://go.microsoft.com/fwlink/p/?LinkId=313374)</span><span class="sxs-lookup"><span data-stu-id="b4e3b-178">For information on how to install AD FS 2.0, see [AD FS 2.0 Step-by-Step and How To Guides](https://go.microsoft.com/fwlink/p/?LinkId=313374).</span></span>

> [!NOTE]
> <span data-ttu-id="b4e3b-179">При установке AD FS 2.0 не добавляйте роль служб федерации Active Directory с помощью диспетчера Windows Server.</span><span class="sxs-lookup"><span data-stu-id="b4e3b-179">When installing AD FS 2.0, do not use the Windows Server Manager to add the Active Directory Federation Services role.</span></span> <span data-ttu-id="b4e3b-180">Вместо этого скачайте и установите пакет служб федерации [Active Directory 2.0 RTW.](https://go.microsoft.com/fwlink/p/?LinkId=313375)</span><span class="sxs-lookup"><span data-stu-id="b4e3b-180">Instead, download and install the [Active Directory Federation Services 2.0 RTW package](https://go.microsoft.com/fwlink/p/?LinkId=313375).</span></span>

### <a name="to-configure-ad-fs-for-two-factor-authentication"></a><span data-ttu-id="b4e3b-181">Настройка двух коэффициентов проверки подлинности для AD FS</span><span class="sxs-lookup"><span data-stu-id="b4e3b-181">To configure AD FS for two-factor Authentication</span></span>

1. <span data-ttu-id="b4e3b-182">Войдите на компьютер AD FS 2.0 с помощью учетной записи администратора домена.</span><span class="sxs-lookup"><span data-stu-id="b4e3b-182">Log in to the AD FS 2.0 computer using a Domain Admin account.</span></span>

2. <span data-ttu-id="b4e3b-183">Запустите Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b4e3b-183">Start Windows PowerShell.</span></span>

3. <span data-ttu-id="b4e3b-184">В командной Windows PowerShell командной строки запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="b4e3b-184">From the Windows PowerShell command-line, run the following command:</span></span>

  ```PowerShell
  add-pssnapin Microsoft.Adfs.PowerShell
  ```

4. <span data-ttu-id="b4e3b-185">Создайте партнерство с каждым сервером, для которого будет включена пассивная проверка подлинности, вы сможете использовать следующую команду, заменив имя сервера для конкретного развертывания:</span><span class="sxs-lookup"><span data-stu-id="b4e3b-185">Establish a partnership with each server that will be enabled for passive authentication by running the following command, replacing the server name specific to your deployment:</span></span>

  ```PowerShell
  Add-ADFSRelyingPartyTrust -Name SfBPool01-PassiveAuth -MetadataURL https://SfBpool01.contoso.com/passiveauth/federationmetadata/2007-06/federationmetadata.xml
  ```

5. <span data-ttu-id="b4e3b-186">В меню "Администрирование" запустите консоль управления AD FS 2.0.</span><span class="sxs-lookup"><span data-stu-id="b4e3b-186">From the Administrative Tools menu, launch the AD FS 2.0 Management console.</span></span>

6. <span data-ttu-id="b4e3b-187">**Расширйте отношения доверия** с отношениями доверия с  >  **отношениями с отношениями доверия с отношениями доверия.**</span><span class="sxs-lookup"><span data-stu-id="b4e3b-187">Expand **Trust Relationships** > **Relying Party Trusts**.</span></span>

7. <span data-ttu-id="b4e3b-188">Убедитесь, что для Skype для бизнеса Server создано новое доверие.</span><span class="sxs-lookup"><span data-stu-id="b4e3b-188">Verify that a new trust has been created for your Skype for Business Server.</span></span>

8. <span data-ttu-id="b4e3b-189">Создайте и назначьте правило авторизации выдачи для отношения доверия с Windows PowerShell с помощью следующих команд:</span><span class="sxs-lookup"><span data-stu-id="b4e3b-189">Create and assign an Issuance Authorization Rule for your relying party trust using Windows PowerShell by running the following commands:</span></span>

  ```PowerShell
  $IssuanceAuthorizationRules = '@RuleTemplate = "AllowAllAuthzRule" => issue(Type = "https://schemas.microsoft.com/authorization/claims/permit", Value = "true");'
  ```

  ```PowerShell
  Set-ADFSRelyingPartyTrust -TargetName SfBPool01-PassiveAuth
-IssuanceAuthorizationRules $IssuanceAuthorizationRules
  ```

9. <span data-ttu-id="b4e3b-190">Создайте и назначьте правило преобразования выдачи для отношения доверия с Windows PowerShell с помощью следующих команд:</span><span class="sxs-lookup"><span data-stu-id="b4e3b-190">Create and assign an Issuance Transform Rule for your relying party trust using Windows PowerShell by running the following commands:</span></span>

  ```PowerShell
  $IssuanceTransformRules = '@RuleTemplate = "PassThroughClaims" @RuleName = "Sid" c:[Type == "https://schemas.microsoft.com/ws/2008/06/identity/claims/primarysid"]=> issue(claim = c);'
  ```

  ```PowerShell
  Set-ADFSRelyingPartyTrust -TargetName SfBPool01-PassiveAuth -IssuanceTransformRules $IssuanceTransformRules
  ```

10. <span data-ttu-id="b4e3b-191">В консоли управления AD FS 2.0 щелкните правой кнопкой мыши отношения доверия с вашей стороной и выберите "Изменить **правила утверждений".**</span><span class="sxs-lookup"><span data-stu-id="b4e3b-191">From the AD FS 2.0 Management console, right click on your relying party trust and select **Edit Claim Rules**.</span></span>

11. <span data-ttu-id="b4e3b-192">Выберите **вкладку "Правила авторизации** выдачи" и убедитесь, что новое правило авторизации успешно создано.</span><span class="sxs-lookup"><span data-stu-id="b4e3b-192">Select the **Issuance Authorization Rules** tab and verify that the new authorization rule was created successfully.</span></span>

12. <span data-ttu-id="b4e3b-193">Выберите **вкладку "Правила преобразования** выдачи" и убедитесь, что новое правило преобразования успешно создано.</span><span class="sxs-lookup"><span data-stu-id="b4e3b-193">Select the **Issuance Transform Rules** tab and verify that the new transform rule was created successfully.</span></span>

## <a name="configuring-ad-fs-20-to-support-client-authentication"></a><span data-ttu-id="b4e3b-194">Настройка AD FS 2.0 для поддержки проверки подлинности клиентов</span><span class="sxs-lookup"><span data-stu-id="b4e3b-194">Configuring AD FS 2.0 to support client authentication</span></span>

<span data-ttu-id="b4e3b-195">Существует два возможных типа проверки подлинности, которые можно настроить, чтобы разрешить AD FS 2.0 поддерживать проверку подлинности с помощью смарт-карт:</span><span class="sxs-lookup"><span data-stu-id="b4e3b-195">There are two possible authentication types that can be configured to allow AD FS 2.0 to support authentication using smart cards:</span></span>

- <span data-ttu-id="b4e3b-196">Проверка подлинности на основе форм (FBA)</span><span class="sxs-lookup"><span data-stu-id="b4e3b-196">Forms-based authentication (FBA)</span></span>

- <span data-ttu-id="b4e3b-197">Проверка подлинности клиента транспортного уровня</span><span class="sxs-lookup"><span data-stu-id="b4e3b-197">Transport Layer Security Client Authentication</span></span>

<span data-ttu-id="b4e3b-198">С помощью проверки подлинности на основе форм можно разработать веб-страницу, которая позволяет пользователям проверить подлинность с помощью имени пользователя или пароля или смарт-карты и ПИН-кода.</span><span class="sxs-lookup"><span data-stu-id="b4e3b-198">Using forms-based authentication, you can develop a web page that allows users to authenticate either by using their username/password or by using their smart card and PIN.</span></span> <span data-ttu-id="b4e3b-199">В этом разделе основное внимание уделяется реализации проверки подлинности клиента на уровне транспорта с помощью AD FS 2.0.</span><span class="sxs-lookup"><span data-stu-id="b4e3b-199">This topic focuses on how to implement Transport Layer Security Client Authentication with AD FS 2.0.</span></span> <span data-ttu-id="b4e3b-200">Дополнительные сведения о типах проверки подлинности AD [](https://go.microsoft.com/fwlink/p/?LinkId=313384)FS 2.0 см. в этой теме.</span><span class="sxs-lookup"><span data-stu-id="b4e3b-200">For more information about AD FS 2.0 authentication types, see [AD FS 2.0: How to Change the Local Authentication Type](https://go.microsoft.com/fwlink/p/?LinkId=313384).</span></span>

### <a name="to-configure-ad-fs-20-to-support-client-authentication"></a><span data-ttu-id="b4e3b-201">Настройка AD FS 2.0 для поддержки проверки подлинности клиентов</span><span class="sxs-lookup"><span data-stu-id="b4e3b-201">To Configure AD FS 2.0 to Support Client Authentication</span></span>

1. <span data-ttu-id="b4e3b-202">Войдите на компьютер AD FS 2.0 с помощью учетной записи администратора домена.</span><span class="sxs-lookup"><span data-stu-id="b4e3b-202">Log in to the AD FS 2.0 computer using a Domain Admin account.</span></span>

2. <span data-ttu-id="b4e3b-203">Запустите проводник Windows.</span><span class="sxs-lookup"><span data-stu-id="b4e3b-203">Launch Windows Explorer.</span></span>

3. <span data-ttu-id="b4e3b-204">Перейдите в C:\inetpub\adfs\ls</span><span class="sxs-lookup"><span data-stu-id="b4e3b-204">Browse to C:\inetpub\adfs\ls</span></span>

4. <span data-ttu-id="b4e3b-205">Сделайте резервную копию существующего web.config файла.</span><span class="sxs-lookup"><span data-stu-id="b4e3b-205">Make a backup copy of the existing web.config file.</span></span>

5. <span data-ttu-id="b4e3b-206">Откройте существующий web.config с помощью Блокнота.</span><span class="sxs-lookup"><span data-stu-id="b4e3b-206">Open the existing web.config file using Notepad.</span></span>

6. <span data-ttu-id="b4e3b-207">В панели меню выберите пункт **"Правка",** а затем выберите **"Найти".**</span><span class="sxs-lookup"><span data-stu-id="b4e3b-207">From the Menu bar, select **Edit** and then select **Find**.</span></span>

7. <span data-ttu-id="b4e3b-208">Поиск по \<localAuthenticationTypes\> запросу .</span><span class="sxs-lookup"><span data-stu-id="b4e3b-208">Search for \<localAuthenticationTypes\>.</span></span>

    <span data-ttu-id="b4e3b-209">Обратите внимание, что в списке перечислены четыре типа проверки подлинности, по одному на строку.</span><span class="sxs-lookup"><span data-stu-id="b4e3b-209">Note that there are four authentication types listed, one per line.</span></span>

8. <span data-ttu-id="b4e3b-210">Переместите строку, содержащую тип проверки подлинности TLSClient, в верхнюю часть списка в разделе.</span><span class="sxs-lookup"><span data-stu-id="b4e3b-210">Move the line containing the TLSClient authentication type to the top of the list in the section.</span></span>

9. <span data-ttu-id="b4e3b-211">Сохраните и закроите web.config файла.</span><span class="sxs-lookup"><span data-stu-id="b4e3b-211">Save and Close the web.config file.</span></span>

10. <span data-ttu-id="b4e3b-212">Запустите командную подсказку с повышенными привилегиями.</span><span class="sxs-lookup"><span data-stu-id="b4e3b-212">Launch a Command Prompt with elevated privileges.</span></span>

11. <span data-ttu-id="b4e3b-213">Перезапустите IIS с помощью следующей команды:</span><span class="sxs-lookup"><span data-stu-id="b4e3b-213">Restart IIS by running the following command:</span></span>

  ```console
  IISReset /Restart /NoForce
  ```

## <a name="configuring-skype-for-business-server-passive-authentication"></a><span data-ttu-id="b4e3b-214">Настройка пассивной проверки подлинности Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="b4e3b-214">Configuring Skype for Business Server passive authentication</span></span>

<span data-ttu-id="b4e3b-215">В следующем разделе описывается настройка Skype для бизнеса Server для поддержки пассивной проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="b4e3b-215">The following section describes how to configure Skype for Business Server to support passive authentication.</span></span> <span data-ttu-id="b4e3b-216">После включения пользователям, для которых включена двух коэффициентная проверка подлинности, потребуется использовать физическую или виртуальную смарт-карту и действительный ПИН-код для входа в клиент Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="b4e3b-216">Once enabled, users who are enabled for two-factor authentication will be required to use a physical or virtual smart card and a valid PIN to sign in using the Skype for Business client.</span></span>

> [!NOTE]
> <span data-ttu-id="b4e3b-217">Настоятельно рекомендуется, чтобы клиенты могли включить пассивную проверку подлинности для регистратора и веб-служб на уровне службы.</span><span class="sxs-lookup"><span data-stu-id="b4e3b-217">It is strongly recommended that customers enable passive authentication for Registrar and Web Services at the service level.</span></span> <span data-ttu-id="b4e3b-218">Если для регистратора и веб-служб включена пассивная проверка подлинности на глобальном уровне, скорее всего, это приведет к сбоям проверки подлинности на уровне организации для пользователей, которые не въехывают с поддерживаемым классическим клиентом.</span><span class="sxs-lookup"><span data-stu-id="b4e3b-218">If passive authentication is enabled for Registrar and Web Services at the global level, it will likely result in organization-wide authentication failures for users who are not signing in with the supported desktop client.</span></span>

### <a name="web-service-configuration"></a><span data-ttu-id="b4e3b-219">Конфигурация веб-службы</span><span class="sxs-lookup"><span data-stu-id="b4e3b-219">Web Service Configuration</span></span>

<span data-ttu-id="b4e3b-220">Далее описано, как создать настраиваемую конфигурацию веб-служб для директоров, корпоративных пулов и серверов Standard Edition, которая будет включена для пассивной проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="b4e3b-220">The following steps describe how to create a custom web service configuration for Directors, Enterprise Pools, and Standard Edition servers that will be enabled for passive authentication.</span></span>

### <a name="to-create-a-custom-web-service-configuration"></a><span data-ttu-id="b4e3b-221">Создание настраиваемой конфигурации веб-службы</span><span class="sxs-lookup"><span data-stu-id="b4e3b-221">To create a custom web service configuration</span></span>

1. <span data-ttu-id="b4e3b-222">Войдите на сервер переднего сервера Skype для бизнеса Server с помощью учетной записи администратора Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="b4e3b-222">Log in to your Skype for Business Server Front End server using a Skype for Business administrator account.</span></span>

2. <span data-ttu-id="b4e3b-223">Запустите оболочку управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="b4e3b-223">Launch the Skype for Business Server Management Shell.</span></span>

3. <span data-ttu-id="b4e3b-224">В командной строке командной строки командной строки Skype для бизнеса Server создайте новую конфигурацию веб-службы для каждого директора, корпоративного пула и сервера Standard Edition, для которых будет включена пассивная проверка подлинности, вы можете использовать следующую команду:</span><span class="sxs-lookup"><span data-stu-id="b4e3b-224">From the Skype for Business Server Management Shell command-line, create a new Web Service configuration for each Director, Enterprise Pool, and Standard Edition server that will be enabled for passive authentication by running the following command:</span></span>

  ```PowerShell
  New-CsWebServiceConfiguration -Identity "Service:WebServer:SfBPool01.contoso.com" -UseWsFedPassiveAuth $true -WsFedPassiveMetadataUri https://dc.contoso.com/federationmetadata/2007-06/federationmetadata.xml
  ```

    > [!CAUTION]
    > <span data-ttu-id="b4e3b-225">ЗначениеМ FQDN WsFedPassiveMetadataUri является имя службы федерации сервера AD FS 2.0.</span><span class="sxs-lookup"><span data-stu-id="b4e3b-225">The value for the WsFedPassiveMetadataUri FQDN is the Federation Service Name of your AD FS 2.0 server.</span></span> <span data-ttu-id="b4e3b-226">Значение "Имя службы федерации" можно найти в консоли управления AD FS  2.0, щелкнув правой кнопкой мыши службу в области навигации и выбрав "Изменить свойства службы федерации". </span><span class="sxs-lookup"><span data-stu-id="b4e3b-226">The Federation Service Name value can be found in the AD FS 2.0 Management Console by right-clicking on **Service** from the navigation pane and then selecting **Edit Federation Service Properties**.</span></span>

4. <span data-ttu-id="b4e3b-227">Убедитесь, что значения UseWsFedPassiveAuth и WsFedPassiveMetadataUri заданы правильно, выдав следующую команду:</span><span class="sxs-lookup"><span data-stu-id="b4e3b-227">Verify that the UseWsFedPassiveAuth and WsFedPassiveMetadataUri values were set correctly by running the following command:</span></span>

  ```PowerShell
  Get-CsWebServiceConfiguration -identity "Service:WebServer:SfBPool01.contoso.com" | format-list UseWsFedPassiveAuth, WsFedPassiveMetadataUri
  ```

5. <span data-ttu-id="b4e3b-228">Для клиентов пассивная проверка подлинности является наименее предпочтительным методом проверки подлинности webticket.</span><span class="sxs-lookup"><span data-stu-id="b4e3b-228">For clients, Passive Authentication is the least preferred authentication method for webticket authentication.</span></span> <span data-ttu-id="b4e3b-229">Для всех директоров, корпоративных пулов и серверов Standard Edition, на которые будет включена пассивная проверка подлинности, все остальные типы проверки подлинности должны быть отключены в веб-службах Skype для бизнеса с помощью следующего cmdlet:</span><span class="sxs-lookup"><span data-stu-id="b4e3b-229">For all Directors, Enterprise Pools, and Standard Edition servers that will be enabled for passive authentication, all other authentication types must be disabled in Skype for Business Web Services by running the following cmdlet:</span></span>

  ```PowerShell
  Set-CsWebServiceConfiguration -Identity "Service:WebServer:SfBPool01.contoso.com" -UseCertificateAuth $false -UsePinAuth $false -UseWindowsAuth NONE
  ```

6. <span data-ttu-id="b4e3b-230">Убедитесь, что все остальные типы проверки подлинности успешно отключены, вы можете с помощью следующего:</span><span class="sxs-lookup"><span data-stu-id="b4e3b-230">Verify that all other authentication types have been successfully disabled by running the following cmdlet:</span></span>

  ```PowerShell
  Get-CsWebServiceConfiguration -Identity "Service:WebServer:SfBPool01.contoso.com" | format-list UseCertificateAuth, UsePinAuth, UseWindowsAuth
  ```

### <a name="proxy-configuration"></a><span data-ttu-id="b4e3b-231">Конфигурация прокси-сервера</span><span class="sxs-lookup"><span data-stu-id="b4e3b-231">Proxy Configuration</span></span>

<span data-ttu-id="b4e3b-232">Если для веб-служб Skype для бизнеса отключена проверка подлинности на сертификате, клиент Skype для бизнеса будет использовать менее предпочтительный тип проверки подлинности, например Kerberos или NTLM, для проверки подлинности в службе Регистратора.</span><span class="sxs-lookup"><span data-stu-id="b4e3b-232">When certificate authentication is disabled for Skype for Business Web Services, the Skype for Business client will use a less preferred authentication type, such as Kerberos or NTLM, to authenticate to the Registrar service.</span></span> <span data-ttu-id="b4e3b-233">Проверка подлинности на сертификате по-прежнему необходима, чтобы клиент извлечения webticket, однако Kerberos и NTLM должны быть отключены для службы регистратора.</span><span class="sxs-lookup"><span data-stu-id="b4e3b-233">Certificate authentication is still needed to allow the client to retrieve a webticket, however, Kerberos and NTLM must be disabled for the Registrar service.</span></span>

<span data-ttu-id="b4e3b-234">Ниже описано, как создать настраиваемую конфигурацию прокси-сервера для пулов, корпоративных пулов и серверов Standard Edition, которые будут включены для пассивной проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="b4e3b-234">The following steps describe how to create a custom proxy configuration for Edge Pools, Enterprise Pools, and Standard Edition servers that will be enabled for passive authentication.</span></span>

### <a name="to-create-a-custom-proxy-configuration"></a><span data-ttu-id="b4e3b-235">Создание настраиваемой конфигурации прокси-сервера</span><span class="sxs-lookup"><span data-stu-id="b4e3b-235">To create a custom proxy configuration</span></span>

1. <span data-ttu-id="b4e3b-236">В командной строке командной строки командной строки Skype для бизнеса Server создайте новую конфигурацию прокси-сервера для каждого пула skype для бизнеса Server, корпоративного пула и сервера Standard Edition, для которых будет включена пассивная проверка подлинности, вы можете использовать следующие команды:</span><span class="sxs-lookup"><span data-stu-id="b4e3b-236">From the Skype for Business Server Management Shell command-line, create a new proxy configuration for each Skype for Business Server Edge Pool, Enterprise Pool, and Standard Edition server that will be enabled for passive authentication by running the following commands:</span></span>

  ```PowerShell
  New-CsProxyConfiguration -Identity "Service:EdgeServer:EdgePool01.contoso.com" -UseKerberosForClientToProxyAuth $False -UseNtlmForClientToProxyAuth $False
  ```

  ```PowerShell
  New-CsProxyConfiguration -Identity "Service:Registrar:SfBPool01.contoso.com" -UseKerberosForClientToProxyAuth $False -UseNtlmForClientToProxyAuth $False
  ```

2. <span data-ttu-id="b4e3b-237">Убедитесь, что все остальные типы проверки подлинности прокси-сервера успешно отключены, выработав следующую команду:</span><span class="sxs-lookup"><span data-stu-id="b4e3b-237">Verify that all other proxy authentication types have been successfully disabled by running the following command:</span></span>

  ```PowerShell
  Get-CsProxyConfiguration -Identity "Service:Registrar:SfBPool01.contoso.com" | format-list UseKerberosForClientToProxyAuth, UseNtlmForClientToProxyAuth, UseCertifcateForClientToProxyAuth
  ```

## <a name="see-also"></a><span data-ttu-id="b4e3b-238">См. также</span><span class="sxs-lookup"><span data-stu-id="b4e3b-238">See also</span></span>

[<span data-ttu-id="b4e3b-239">Управление двух-факторной проверкой подлинности в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="b4e3b-239">Manage two-factor authentication in Skype for Business Server</span></span>](two-factor-authentication.md)

[<span data-ttu-id="b4e3b-240">Использование двух коэффициентов проверки подлинности в клиенте Skype для бизнеса и Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="b4e3b-240">Use two-factor authentication with Skype for Business client and Skype for Business Server</span></span>](use-two-factor.md)
