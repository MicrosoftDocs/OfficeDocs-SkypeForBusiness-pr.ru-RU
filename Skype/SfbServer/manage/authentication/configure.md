---
title: Настройка двухфакторной проверки подлинности в Скайп для Business Server
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: c24e0891-e108-4cb6-9902-c6a4c8e68455
description: 'Сводка: Настройка двухфакторной проверки подлинности в Скайп для Business Server.'
ms.openlocfilehash: 4fc8791cd7459ecea89bb8101b2c1a488b6eace2
ms.sourcegitcommit: 08c6fe9955ea61dd9cded2210ae0153e06bdd8a6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/28/2018
ms.locfileid: "23250803"
---
# <a name="configure-two-factor-authentication-in-skype-for-business-server"></a><span data-ttu-id="73542-103">Настройка двухфакторной проверки подлинности в Скайп для Business Server</span><span class="sxs-lookup"><span data-stu-id="73542-103">Configure two-factor authentication in Skype for Business Server</span></span>

<span data-ttu-id="73542-104">**Сводка:** Настройка двухфакторной проверки подлинности в Скайп для Business Server.</span><span class="sxs-lookup"><span data-stu-id="73542-104">**Summary:** Configure two-factor authentication in Skype for Business Server.</span></span>

<span data-ttu-id="73542-105">В следующих разделах приведена пошаговая процедура настройки двухфакторной проверки подлинности для развертывания.</span><span class="sxs-lookup"><span data-stu-id="73542-105">The following sections describe the steps necessary to configure two-factor authentication for your deployment.</span></span> <span data-ttu-id="73542-106">Дополнительные сведения о двухфакторной проверки подлинности можно [многофакторная проверка подлинности Включение Office 365 для администраторов online - Post пользователя сетки](https://go.microsoft.com/fwlink/p/?LinkId=313332).</span><span class="sxs-lookup"><span data-stu-id="73542-106">For more information about Two-factor authentication, see [Enabling Office 365 multi-factor authentication for online administrators - Grid User Post](https://go.microsoft.com/fwlink/p/?LinkId=313332).</span></span>

## <a name="configure-an-enterprise-root-certificate-authority-to-support-smart-card-authentication"></a><span data-ttu-id="73542-107">Настройка корневого центра сертификации на предприятии для проверки подлинности с помощью смарт-карт</span><span class="sxs-lookup"><span data-stu-id="73542-107">Configure an Enterprise Root Certificate Authority to Support Smart Card Authentication</span></span>

<span data-ttu-id="73542-108">Ниже описан порядок действий по настройке корневого ЦС предприятия для проверки подлинности с помощью смарт-карт.</span><span class="sxs-lookup"><span data-stu-id="73542-108">The following steps describe how to configure an Enterprise Root CA to support Smart Card Authentication:</span></span>

<span data-ttu-id="73542-109">Сведения о том, как установить корневой Сертификат предприятия содержатся в разделе [Установка корневой центр сертификации предприятия](https://go.microsoft.com/fwlink/p/?LinkID=313364).</span><span class="sxs-lookup"><span data-stu-id="73542-109">For information on how to install an Enterprise Root CA, see [Install an Enterprise Root Certification Authority](https://go.microsoft.com/fwlink/p/?LinkID=313364).</span></span>

1. <span data-ttu-id="73542-110">Войдите на компьютер ЦС предприятия с учетной записью администратора домена.</span><span class="sxs-lookup"><span data-stu-id="73542-110">Log in to the Enterprise CA computer using a Domain Admin account.</span></span>

2. <span data-ttu-id="73542-111">Запустите приложение System Manager и убедитесь в том, что установлена роль регистрации сертификатов через Интернет.</span><span class="sxs-lookup"><span data-stu-id="73542-111">Launch System Manager, and verify that the Certificate Authority Web Enrollment role is installed.</span></span>

3. <span data-ttu-id="73542-112">В меню **Администрирование** откройте консоль управления **Центр сертификации**.</span><span class="sxs-lookup"><span data-stu-id="73542-112">From the **Administrative Tools** menu, open the **Certification Authority** management console.</span></span>

4. <span data-ttu-id="73542-113">В области навигации разверните элемент **Центр сертификации**.</span><span class="sxs-lookup"><span data-stu-id="73542-113">In the Navigation pane, expand **Certification Authority**.</span></span>

5. <span data-ttu-id="73542-114">Щелкните правой кнопкой **Шаблоны сертификатов** и выберите **Создать**, затем **Выдаваемый шаблон сертификата**.</span><span class="sxs-lookup"><span data-stu-id="73542-114">Right click on **Certificate Templates**, select **New**, then select **Certificate Template to Issue**.</span></span>

6. <span data-ttu-id="73542-115">Выберите **Агент подачи заявок**, **Пользователь со смарт-картой** и **Вход со смарт-картой**.</span><span class="sxs-lookup"><span data-stu-id="73542-115">Select **Enrollment Agent**, **Smartcard User**, and **Smartcard Logon**.</span></span>

7. <span data-ttu-id="73542-116">Нажмите **ОК**.</span><span class="sxs-lookup"><span data-stu-id="73542-116">Click **OK**.</span></span>

8. <span data-ttu-id="73542-117">Щелкните **Шаблоны сертификатов** правой кнопкой мыши.</span><span class="sxs-lookup"><span data-stu-id="73542-117">Right click on **Certificate Templates**.</span></span>

9. <span data-ttu-id="73542-118">Выберите **Управление**.</span><span class="sxs-lookup"><span data-stu-id="73542-118">Select **Manage**.</span></span>

10. <span data-ttu-id="73542-119">Откройте свойства шаблона пользователя смарт-карты.</span><span class="sxs-lookup"><span data-stu-id="73542-119">Open the properties of the Smartcard User template.</span></span>

11. <span data-ttu-id="73542-120">Перейдите на вкладку **Безопасность**.</span><span class="sxs-lookup"><span data-stu-id="73542-120">Click on the **Security** tab.</span></span>

12. <span data-ttu-id="73542-121">Задайте указанные ниже разрешения.</span><span class="sxs-lookup"><span data-stu-id="73542-121">Change the permissions as follows:</span></span>

    - <span data-ttu-id="73542-122">Добавьте учетные записи отдельных пользователей Active Directory с разрешениями на чтение и подачу заявок (разрешить).</span><span class="sxs-lookup"><span data-stu-id="73542-122">Add individual user AD accounts with Read/Enroll (Allow) permissions, or</span></span>

    - <span data-ttu-id="73542-123">Добавьте группу безопасности с пользователями смарт-карт, обладающую разрешениями на чтение и подачу заявок (разрешить).</span><span class="sxs-lookup"><span data-stu-id="73542-123">Add a security group containing smart card users with Read/Enroll (Allow) permissions, or</span></span>

    - <span data-ttu-id="73542-124">Добавьте группу пользователей домена с разрешениями на чтение и подачу заявок (разрешить).</span><span class="sxs-lookup"><span data-stu-id="73542-124">Add the Domain Users group with Read/Enroll (Allow) permissions</span></span>

## <a name="configure-windows-8-for-virtual-smart-cards"></a><span data-ttu-id="73542-125">Настройка Windows 8 для виртуальных смарт-карт</span><span class="sxs-lookup"><span data-stu-id="73542-125">Configure Windows 8 for Virtual Smart Cards</span></span>

<span data-ttu-id="73542-126">Одним их факторов, которые следует учитывать при развертывании двухфакторной проверки подлинности и технологии смарт-карт, является его стоимость.</span><span class="sxs-lookup"><span data-stu-id="73542-126">One factor to consider when deploying two-factor authentication and smart card technology is the cost of implementation.</span></span> <span data-ttu-id="73542-127">Windows 8 предоставляет ряд новых функций безопасности и одним из наиболее интересных новых функций является поддержка виртуального смарт-карт.</span><span class="sxs-lookup"><span data-stu-id="73542-127">Windows 8 provides a number of new security capabilities, and one of the most interesting new features is support for virtual smart cards.</span></span>

<span data-ttu-id="73542-128">Если компьютеры оборудованы микросхемами доверенного платформенного модуля (TPM), соответствующими спецификации версии 1.2, организации могут пользоваться преимуществами регистрации по смарт-картам без дополнительных капиталовложений в оборудование.</span><span class="sxs-lookup"><span data-stu-id="73542-128">For computers equipped with a Trusted Platform Module (TPM) chip that meets specification version 1.2, organizations can now get the benefits of smart card logon without making any additional investments in hardware.</span></span> <span data-ttu-id="73542-129">Дополнительные сведения можно [с помощью виртуальных смарт-карт с Windows 8](https://go.microsoft.com/fwlink/p/?LinkId=313365).</span><span class="sxs-lookup"><span data-stu-id="73542-129">For more information, see [Using Virtual Smart Cards with Windows 8](https://go.microsoft.com/fwlink/p/?LinkId=313365).</span></span>

### <a name="to-configure-windows-8-for-virtual-smart-cards"></a><span data-ttu-id="73542-130">Настройка конфигурации Windows 8 для виртуальных смарт-карт</span><span class="sxs-lookup"><span data-stu-id="73542-130">To Configure Windows 8 for Virtual Smart Cards</span></span>

1. <span data-ttu-id="73542-131">Войдите компьютер Windows 8, используя учетные данные Скайп для пользователя с включенной поддержкой бизнеса.</span><span class="sxs-lookup"><span data-stu-id="73542-131">Log in to the Windows 8 computer using the credentials of a Skype for Business-enabled user.</span></span>

2. <span data-ttu-id="73542-132">На начальном экране Windows 8 переместите курсор в нижний правый угол.</span><span class="sxs-lookup"><span data-stu-id="73542-132">At the Windows 8 Start screen, move your cursor to the bottom right corner of the screen.</span></span>

3. <span data-ttu-id="73542-133">Выберите параметр **поиска** и затем выполните поиск forCommand строки.</span><span class="sxs-lookup"><span data-stu-id="73542-133">Select the **Search** option, and then search forCommand Prompt.</span></span>

4. <span data-ttu-id="73542-134">Щелкните **Командная строка** правой кнопкой мыши, затем выберите **Запуск от имени администратора**.</span><span class="sxs-lookup"><span data-stu-id="73542-134">Right click on **Command Prompt**, and then select **Run as Administrator**.</span></span>

5. <span data-ttu-id="73542-135">Откройте консоль управления TPM, выполнив следующую команду:</span><span class="sxs-lookup"><span data-stu-id="73542-135">Open the Trusted Platform Module (TPM) Management console by running the following command:</span></span>

  ```
  Tpm.msc
  ```

6. <span data-ttu-id="73542-136">Убедитесь в том, что спецификация вашего TPM имеет версию 1.2 или выше.</span><span class="sxs-lookup"><span data-stu-id="73542-136">From the TPM management console, verify that your TPM specification version is at least 1.2</span></span>

    > [!NOTE]
    > <span data-ttu-id="73542-137">При появлении диалогового окна с сообщением, что совместимый TPM не найден, убедитесь в том, что ваш компьютер имеет совместимый модуль TPM и что он включен в BIOS компьютера.</span><span class="sxs-lookup"><span data-stu-id="73542-137">If you receive a dialog stating that a Compatible Trust Platform Module (TPM) cannot be found, verify that the computer has a compatible TPM module and that it is enabled in the system BIOS.</span></span>

7. <span data-ttu-id="73542-138">Закройте консоль управления TPM</span><span class="sxs-lookup"><span data-stu-id="73542-138">Close the TPM management console</span></span>

8. <span data-ttu-id="73542-139">Создайте новую виртуальную смарт-карту, введя в командную строку следующую команду:</span><span class="sxs-lookup"><span data-stu-id="73542-139">From the command prompt, create a new virtual smart card using the following command:</span></span>

  ```
  TpmVscMgr create /name MyVSC /pin default /adminkey random /generate
  ```

    > [!NOTE]
    > <span data-ttu-id="73542-140">Чтобы сообщить настраиваемое значение ПИН-кода, используйте ключ командной строки /pin.</span><span class="sxs-lookup"><span data-stu-id="73542-140">To provide a custom PIN value when creating the virtual smart card, use /pin prompt instead.</span></span>

9. <span data-ttu-id="73542-141">Откройте консоль управления компьютером, введя в командную строку следующую команду:</span><span class="sxs-lookup"><span data-stu-id="73542-141">From the command prompt, open the Computer Management console by running the following command:</span></span>

  ```
  CompMgmt.msc
  ```

10. <span data-ttu-id="73542-142">В консоли управления компьютером выберите **Управление устройствами**.</span><span class="sxs-lookup"><span data-stu-id="73542-142">In the Computer Management console, select **Device Management**.</span></span>

11. <span data-ttu-id="73542-143">Разверните элемент **Устройства чтения смарт-карт**.</span><span class="sxs-lookup"><span data-stu-id="73542-143">Expand **Smart card readers**.</span></span>

12. <span data-ttu-id="73542-144">Убедитесь в том, что создание нового устройства для чтения виртуальной смарт-карты успешно завершено.</span><span class="sxs-lookup"><span data-stu-id="73542-144">Verify that the new virtual smart card reader has been created successfully.</span></span>

## <a name="enroll-users-for-smart-card-authentication"></a><span data-ttu-id="73542-145">Регистрация пользователей для проверки подлинности по смарт-карте</span><span class="sxs-lookup"><span data-stu-id="73542-145">Enroll users for smart card authentication</span></span>

<span data-ttu-id="73542-p104">Зарегистрировать пользователей для проверки подлинности с помощью смарт-карты можно двумя способами. Простой вариант — поручить пользователям самостоятельно зарегистрироваться с помощью функции регистрации через Интернет, в то время как сложный связан с использованием агента регистрации. В этом разделе рассматривается процедура самостоятельной регистрации для использования сертификатов смарт-карт.</span><span class="sxs-lookup"><span data-stu-id="73542-p104">There are generally two methods for enrolling users for smart card authentication. The easier method involves having users enroll directly for smart card authentication using web enrollment, while the more complex method involves using an enrollment agent. This topic focuses on self-enrollment for smartcard certificates.</span></span>

<span data-ttu-id="73542-149">Дополнительные сведения о регистрации от имени пользователей и как агент регистрации видеть [Заявка на сертификаты от имени других пользователей](https://go.microsoft.com/fwlink/p/?LinkID=313367).</span><span class="sxs-lookup"><span data-stu-id="73542-149">For more information on enrolling on behalf of users as an enrollment agent, see [Enroll for Certificates on Behalf of Other Users](https://go.microsoft.com/fwlink/p/?LinkID=313367).</span></span>

### <a name="to-enroll-users-for-smart-card-authentication"></a><span data-ttu-id="73542-150">Порядок регистрации пользователей для проверки подлинности с помощью смарт-карты</span><span class="sxs-lookup"><span data-stu-id="73542-150">To Enroll Users for Smart Card Authentication</span></span>

1. <span data-ttu-id="73542-151">Выполните вход рабочая станция Windows 8, используя учетные данные Скайп для пользователя с включенной поддержкой Business.</span><span class="sxs-lookup"><span data-stu-id="73542-151">Log in to the Windows 8 workstation using the credentials of a Skype for Business-enabled user.</span></span>

2. <span data-ttu-id="73542-152">Запустите браузер Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="73542-152">Launch Internet Explorer.</span></span>

3. <span data-ttu-id="73542-153">Перейдите на страницу **Сертификат центра сертификации подача заявок через Интернет** (например https://MyCA.contoso.com/certsrv).</span><span class="sxs-lookup"><span data-stu-id="73542-153">Browse to the **Certificate Authority Web Enrollment** page (e.g. https://MyCA.contoso.com/certsrv).</span></span>

    > [!NOTE]
    > <span data-ttu-id="73542-154">В браузере Internet Explorer 10 эту страницу, возможно, потребуется открыть в режиме совместимости.</span><span class="sxs-lookup"><span data-stu-id="73542-154">If you are using Internet Explorer 10, you may need to view this website in Compatibility Mode.</span></span>

4. <span data-ttu-id="73542-155">На странице **приветствия** выберите **Запросить сертификат**.</span><span class="sxs-lookup"><span data-stu-id="73542-155">On the **Welcome** Page, select **Request a certificate**.</span></span>

5. <span data-ttu-id="73542-156">Затем выберите **Расширенный запрос**.</span><span class="sxs-lookup"><span data-stu-id="73542-156">Next, select **Advanced Request**.</span></span>

6. <span data-ttu-id="73542-157">Выберите **Создать и выдать запрос к этому ЦС**.</span><span class="sxs-lookup"><span data-stu-id="73542-157">Select **Create and submit a request to this CA**.</span></span>

7. <span data-ttu-id="73542-158">В разделе **Шаблон сертификата** выберите **Пользователь смарт-карты** и введите в полях расширенного запроса сертификата следующие значения.</span><span class="sxs-lookup"><span data-stu-id="73542-158">Select **Smartcard User** under the **Certificate Template** section and complete the advanced certificate request with the following values:</span></span>

  - <span data-ttu-id="73542-159">В разделе **Параметры ключа** задайте следующие значения.</span><span class="sxs-lookup"><span data-stu-id="73542-159">**Key Options** confirm he following settings:</span></span>

    - <span data-ttu-id="73542-160">Установите переключатель в положение **Создать новый набор ключей**.</span><span class="sxs-lookup"><span data-stu-id="73542-160">Select the **Create new key set** radio button</span></span>

    - <span data-ttu-id="73542-161">Для параметра **Поставщик служб шифрования** выберите значение **Базовый поставщик криптографии смарт-карт (Microsoft)**.</span><span class="sxs-lookup"><span data-stu-id="73542-161">For **CSP**, select **Microsoft Base Smart Card Crypto Provider**</span></span>

    - <span data-ttu-id="73542-162">Для параметра **Использование ключа** выберите значение **Обмен** (единственное доступное значение).</span><span class="sxs-lookup"><span data-stu-id="73542-162">For **Key Usage**, select **Exchange** (this is the only option available).</span></span>

    - <span data-ttu-id="73542-163">В поле **Размер ключа** введите значение 2048.</span><span class="sxs-lookup"><span data-stu-id="73542-163">For **Key Size**, enter 2048</span></span>

    - <span data-ttu-id="73542-164">Убедитесь в том, что флажок **Автоматическое имя контейнера ключа** установлен.</span><span class="sxs-lookup"><span data-stu-id="73542-164">Confirm that **Automatic key container name** is selected</span></span>

    - <span data-ttu-id="73542-165">Оставьте остальные флажки снятыми.</span><span class="sxs-lookup"><span data-stu-id="73542-165">Leave the other boxes unchecked.</span></span>

  - <span data-ttu-id="73542-166">В разделе **Дополнительные параметры** задайте следующие значения.</span><span class="sxs-lookup"><span data-stu-id="73542-166">Under **Additional Options** confirm the following values:</span></span>

    - <span data-ttu-id="73542-167">Для параметра **Формат запроса** выберите значение **CMC**.</span><span class="sxs-lookup"><span data-stu-id="73542-167">For **Request Format** select **CMC**.</span></span>

    - <span data-ttu-id="73542-168">Для параметра **Алгоритм хэширования** выберите значение **sha1**.</span><span class="sxs-lookup"><span data-stu-id="73542-168">For **Hash Algorithm** select **sha1**.</span></span>

    - <span data-ttu-id="73542-169">Для enterSmardcard **Понятное имя** сертификата.</span><span class="sxs-lookup"><span data-stu-id="73542-169">For **Friendly Name** enterSmardcard Certificate.</span></span>

8. <span data-ttu-id="73542-170">Если используется физическое устройство считывания смарт-карт, вставьте смарт-карту в устройство.</span><span class="sxs-lookup"><span data-stu-id="73542-170">If you are using a physical smartcard reader, insert the smart card into the device.</span></span>

9. <span data-ttu-id="73542-171">Нажмите кнопку **Отправить** для отправки запроса сертификата.</span><span class="sxs-lookup"><span data-stu-id="73542-171">Click **Submit** to submit the certificate request.</span></span>

10. <span data-ttu-id="73542-172">Когда будет предложено, введите ПИН-код, использовавшийся при создании виртуальной смарт-карты.</span><span class="sxs-lookup"><span data-stu-id="73542-172">When prompted, enter the PIN that was used to create the virtual smart card.</span></span>

    > [!NOTE]
    > <span data-ttu-id="73542-173">Значение по умолчанию виртуальный смарт-карт ПИН-КОДОВ: "12345678".</span><span class="sxs-lookup"><span data-stu-id="73542-173">The default virtual smart card PIN value is '12345678'.</span></span>

11. <span data-ttu-id="73542-174">После выдачи сертификата щелкните **Установить этот сертификат** для завершения процедуры регистрации.</span><span class="sxs-lookup"><span data-stu-id="73542-174">Once the certificate has been issued, click **Install this certificate** to complete the enrollment process.</span></span>

    > [!NOTE]
    >  <span data-ttu-id="73542-175">Если ваш запрос на сертификат не удается с ошибкой «этой веб-браузер не поддерживает создание запросы сертификатов», существует три возможных способа устранения проблемы:</span><span class="sxs-lookup"><span data-stu-id="73542-175">If your certificate request fails with the error "This Web browser does not support the generation of certificate requests," there are three possible ways to resolve the issue:</span></span>

        a. Enable Compatibility View in Internet Explorer
        b. Enable the Turn on Intranet settings option in Internet Explorer
        c. Select the Reset all zones to default level setting under the Security tab in the Internet Explorer options menu.

## <a name="configure-active-directory-federation-services-ad-fs-20"></a><span data-ttu-id="73542-176">Настройка служб федерации Active Directory (AD FS 2.0)</span><span class="sxs-lookup"><span data-stu-id="73542-176">Configure Active Directory Federation Services (AD FS 2.0)</span></span>

<span data-ttu-id="73542-177">В этом разделе рассматривается настройка служб федерации Active Directory (AD FS 2.0) для поддержки многофакторной проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="73542-177">The following section describes how to configure Active Directory Federation Services (AD FS 2.0) to support multi-factor authentication.</span></span> <span data-ttu-id="73542-178">Сведения о том, как установить AD FS 2.0 можно [AD FS 2.0 Step-by-Step и как для руководства по](https://go.microsoft.com/fwlink/p/?LinkId=313374).</span><span class="sxs-lookup"><span data-stu-id="73542-178">For information on how to install AD FS 2.0, see [AD FS 2.0 Step-by-Step and How To Guides](https://go.microsoft.com/fwlink/p/?LinkId=313374).</span></span>

> [!NOTE]
> <span data-ttu-id="73542-179">При установке AD FS 2.0 не добавляйте роль службы федерации Active Directory с помощью диспетчера серверов Windows.</span><span class="sxs-lookup"><span data-stu-id="73542-179">When installing AD FS 2.0, do not use the Windows Server Manager to add the Active Directory Federation Services role.</span></span> <span data-ttu-id="73542-180">Вместо этого загрузите и установите [пакет Active Directory Federation Services 2.0 RTW](https://go.microsoft.com/fwlink/p/?LinkId=313375).</span><span class="sxs-lookup"><span data-stu-id="73542-180">Instead, download and install the [Active Directory Federation Services 2.0 RTW package](https://go.microsoft.com/fwlink/p/?LinkId=313375).</span></span>

### <a name="to-configure-ad-fs-for-two-factor-authentication"></a><span data-ttu-id="73542-181">Настройка AD FS для двухфакторной проверки подлинности</span><span class="sxs-lookup"><span data-stu-id="73542-181">To configure AD FS for two-factor Authentication</span></span>

1. <span data-ttu-id="73542-182">Войдите в систему на компьютере с AD FS 2.0 с помощью учетной записи администратора домена.</span><span class="sxs-lookup"><span data-stu-id="73542-182">Log in to the AD FS 2.0 computer using a Domain Admin account.</span></span>

2. <span data-ttu-id="73542-183">Запустите Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="73542-183">Start Windows PowerShell.</span></span>

3. <span data-ttu-id="73542-184">Введите в командной строке Windows PowerShell следующую команду:</span><span class="sxs-lookup"><span data-stu-id="73542-184">From the Windows PowerShell command-line, run the following command:</span></span>

  ```
  add-pssnapin Microsoft.Adfs.PowerShell
  ```

4. <span data-ttu-id="73542-185">Установите партнерское отношение с каждым сервером, на котором будет разрешена пассивная проверка подлинности; для этого выполните следующую команду, указав имя сервера в конкретном развертывании:</span><span class="sxs-lookup"><span data-stu-id="73542-185">Establish a partnership with each server that will be enabled for passive authentication by running the following command, replacing the server name specific to your deployment:</span></span>

  ```
  Add-ADFSRelyingPartyTrust -Name SfBPool01-PassiveAuth -MetadataURL https://SfBpool01.contoso.com/passiveauth/federationmetadata/2007-06/federationmetadata.xml
  ```

5. <span data-ttu-id="73542-186">Запустите консоль управления AD FS 2.0 в меню "Средства администрирования".</span><span class="sxs-lookup"><span data-stu-id="73542-186">From the Administrative Tools menu, launch the AD FS 2.0 Management console.</span></span>

6. <span data-ttu-id="73542-187">Разверните узел **отношения доверия** > **отношения доверия с проверяющей стороной**.</span><span class="sxs-lookup"><span data-stu-id="73542-187">Expand **Trust Relationships** > **Relying Party Trusts**.</span></span>

7. <span data-ttu-id="73542-188">Убедитесь, что нового отношения доверия был создан для вашей Скайп для Business Server.</span><span class="sxs-lookup"><span data-stu-id="73542-188">Verify that a new trust has been created for your Skype for Business Server.</span></span>

8. <span data-ttu-id="73542-189">С помощью Windows PowerShell и следующих команд создайте и назначьте для отношения доверия с проверяющей стороны правило утверждения авторизации:</span><span class="sxs-lookup"><span data-stu-id="73542-189">Create and assign an Issuance Authorization Rule for your relying party trust using Windows PowerShell by running the following commands:</span></span>

  ```
  $IssuanceAuthorizationRules = '@RuleTemplate = "AllowAllAuthzRule" => issue(Type = "https://schemas.microsoft.com/authorization/claims/permit", Value = "true");'
  ```

  ```
  Set-ADFSRelyingPartyTrust -TargetName SfBPool01-PassiveAuth
-IssuanceAuthorizationRules $IssuanceAuthorizationRules
  ```

9. <span data-ttu-id="73542-190">С помощью Windows PowerShell и следующих команд создайте и назначьте для отношения доверия с проверяющей стороны правило утверждения преобразования:</span><span class="sxs-lookup"><span data-stu-id="73542-190">Create and assign an Issuance Transform Rule for your relying party trust using Windows PowerShell by running the following commands:</span></span>

  ```
  $IssuanceTransformRules = '@RuleTemplate = "PassThroughClaims" @RuleName = "Sid" c:[Type == "https://schemas.microsoft.com/ws/2008/06/identity/claims/primarysid"]=> issue(claim = c);'
  ```

  ```
  Set-ADFSRelyingPartyTrust -TargetName SfBPool01-PassiveAuth -IssuanceTransformRules $IssuanceTransformRules
  ```

10. <span data-ttu-id="73542-191">В консоли управления AD FS 2.0 щелкните отношение доверия с проверяющей стороной правой кнопкой мыши и выберите команду **редактирования правил утверждений**.</span><span class="sxs-lookup"><span data-stu-id="73542-191">From the AD FS 2.0 Management console, right click on your relying party trust and select **Edit Claim Rules**.</span></span>

11. <span data-ttu-id="73542-192">Перейдите на вкладку **правил разрешения выпуска** и убедитесь в том, что новое правило разрешения успешно создано.</span><span class="sxs-lookup"><span data-stu-id="73542-192">Select the **Issuance Authorization Rules** tab and verify that the new authorization rule was created successfully.</span></span>

12. <span data-ttu-id="73542-193">Перейдите на вкладку **правил преобразования выпуска** и убедитесь в том, что новое правило преобразования успешно создано.</span><span class="sxs-lookup"><span data-stu-id="73542-193">Select the **Issuance Transform Rules** tab and verify that the new transform rule was created successfully.</span></span>

## <a name="configuring-ad-fs-20-to-support-client-authentication"></a><span data-ttu-id="73542-194">Настройка AD FS 2.0 для поддержки проверки подлинности клиента</span><span class="sxs-lookup"><span data-stu-id="73542-194">Configuring AD FS 2.0 to support client authentication</span></span>

<span data-ttu-id="73542-195">Чтобы разрешить в AD FS 2.0 поддержку проверки подлинности с использованием смарт-карт, можно настроить два указанных ниже типа проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="73542-195">There are two possible authentication types that can be configured to allow AD FS 2.0 to support authentication using smart cards:</span></span>

- <span data-ttu-id="73542-196">Проверка подлинности на основе форм</span><span class="sxs-lookup"><span data-stu-id="73542-196">Forms-based authentication (FBA)</span></span>

- <span data-ttu-id="73542-197">Проверка подлинности клиента по протоколу TLS</span><span class="sxs-lookup"><span data-stu-id="73542-197">Transport Layer Security Client Authentication</span></span>

<span data-ttu-id="73542-198">На основе проверки подлинности по формам можно разработать веб-страницу, где подлинность пользователей будет проверяться по имени и паролю или по смарт-карте и PIN‑коду.</span><span class="sxs-lookup"><span data-stu-id="73542-198">Using forms-based authentication, you can develop a web page that allows users to authenticate either by using their username/password or by using their smart card and PIN.</span></span> <span data-ttu-id="73542-199">В этой статье рассматривается преимущественно реализация проверки подлинности клиента по протоколу TLS с помощью AD FS 2.0.</span><span class="sxs-lookup"><span data-stu-id="73542-199">This topic focuses on how to implement Transport Layer Security Client Authentication with AD FS 2.0.</span></span> <span data-ttu-id="73542-200">Дополнительные сведения о типах AD FS 2.0 проверки подлинности можно [AD FS 2.0: изменение локального типа проверки подлинности](https://go.microsoft.com/fwlink/p/?LinkId=313384).</span><span class="sxs-lookup"><span data-stu-id="73542-200">For more information about AD FS 2.0 authentication types, see [AD FS 2.0: How to Change the Local Authentication Type](https://go.microsoft.com/fwlink/p/?LinkId=313384).</span></span>

### <a name="to-configure-ad-fs-20-to-support-client-authentication"></a><span data-ttu-id="73542-201">Настройка AD FS 2.0 для поддержки проверки подлинности клиента</span><span class="sxs-lookup"><span data-stu-id="73542-201">To Configure AD FS 2.0 to Support Client Authentication</span></span>

1. <span data-ttu-id="73542-202">Войдите в систему на компьютере с AD FS 2.0 с помощью учетной записи администратора домена.</span><span class="sxs-lookup"><span data-stu-id="73542-202">Log in to the AD FS 2.0 computer using a Domain Admin account.</span></span>

2. <span data-ttu-id="73542-203">Запустите проводник.</span><span class="sxs-lookup"><span data-stu-id="73542-203">Launch Windows Explorer.</span></span>

3. <span data-ttu-id="73542-204">Перейдите в папку C:\inetpub\adfs\ls</span><span class="sxs-lookup"><span data-stu-id="73542-204">Browse to C:\inetpub\adfs\ls</span></span>

4. <span data-ttu-id="73542-205">Сделайте резервную копию файла web.config.</span><span class="sxs-lookup"><span data-stu-id="73542-205">Make a backup copy of the existing web.config file.</span></span>

5. <span data-ttu-id="73542-206">Откройте файл web.config с помощью Блокнота.</span><span class="sxs-lookup"><span data-stu-id="73542-206">Open the existing web.config file using Notepad.</span></span>

6. <span data-ttu-id="73542-207">В строке меню выберите **Правка**, затем **Найти**.</span><span class="sxs-lookup"><span data-stu-id="73542-207">From the Menu bar, select **Edit** and then select **Find**.</span></span>

7. <span data-ttu-id="73542-208">Поиск \<localAuthenticationTypes\>.</span><span class="sxs-lookup"><span data-stu-id="73542-208">Search for \<localAuthenticationTypes\>.</span></span>

    <span data-ttu-id="73542-209">Обратите внимание, что здесь будут перечислены четыре типа проверки подлинности, по одному на строку.</span><span class="sxs-lookup"><span data-stu-id="73542-209">Note that there are four authentication types listed, one per line.</span></span>

8. <span data-ttu-id="73542-210">Переместите строку, содержащую тип проверки подлинности TLSClient, в начало списка в разделе.</span><span class="sxs-lookup"><span data-stu-id="73542-210">Move the line containing the TLSClient authentication type to the top of the list in the section.</span></span>

9. <span data-ttu-id="73542-211">Сохраните и закройте файл web.config.</span><span class="sxs-lookup"><span data-stu-id="73542-211">Save and Close the web.config file.</span></span>

10. <span data-ttu-id="73542-212">Запустите командную строку с повышенными привилегиями.</span><span class="sxs-lookup"><span data-stu-id="73542-212">Launch a Command Prompt with elevated privileges.</span></span>

11. <span data-ttu-id="73542-213">Перезапустите службу IIS, выполнив следующую команду:</span><span class="sxs-lookup"><span data-stu-id="73542-213">Restart IIS by running the following command:</span></span>

  ```
  IISReset /Restart /NoForce
  ```

## <a name="configuring-skype-for-business-server-passive-authentication"></a><span data-ttu-id="73542-214">Настройка пассивной проверки подлинности в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="73542-214">Configuring Skype for Business Server passive authentication</span></span>

<span data-ttu-id="73542-215">В следующем разделе описывается настройка Скайп для Business Server для поддержки пассивной проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="73542-215">The following section describes how to configure Skype for Business Server to support passive authentication.</span></span> <span data-ttu-id="73542-216">Если этот параметр включен, пользователи, которым разрешена двухфакторной проверки подлинности требуется указать использование физических или виртуальных смарт-карт и действительный ПИН-код для вход при помощи Скайп для клиента Business.</span><span class="sxs-lookup"><span data-stu-id="73542-216">Once enabled, users who are enabled for two-factor authentication will be required to use a physical or virtual smart card and a valid PIN to sign in using the Skype for Business client.</span></span>

> [!NOTE]
> <span data-ttu-id="73542-p109">Заказчикам настоятельно рекомендуется включить пассивную проверку подлинности для регистратора и веб-служб на уровне служб. Включение пассивной проверки подлинности включена для регистратора и веб-служб на глобальном уровне с большой вероятностью приводит к сбоям проверки подлинности пользователей, входящих не с поддерживаемых клиентов для настольных компьютеров, во всей организации.</span><span class="sxs-lookup"><span data-stu-id="73542-p109">It is strongly recommended that customers enable passive authentication for Registrar and Web Services at the service level. If passive authentication is enabled for Registrar and Web Services at the global level, it will likely result in organization-wide authentication failures for users who are not signing in with the supported desktop client.</span></span>

### <a name="web-service-configuration"></a><span data-ttu-id="73542-219">Конфигурация веб-служб</span><span class="sxs-lookup"><span data-stu-id="73542-219">Web Service Configuration</span></span>

<span data-ttu-id="73542-220">Ниже описана процедура создания настраиваемой конфигурации веб-служб для директоров, корпоративных пулов и серверов Standard Edition, для которых будет включена пассивная проверка подлинности.</span><span class="sxs-lookup"><span data-stu-id="73542-220">The following steps describe how to create a custom web service configuration for Directors, Enterprise Pools, and Standard Edition servers that will be enabled for passive authentication.</span></span>

### <a name="to-create-a-custom-web-service-configuration"></a><span data-ttu-id="73542-221">Порядок создания настраиваемой конфигурации веб-служб</span><span class="sxs-lookup"><span data-stu-id="73542-221">To create a custom web service configuration</span></span>

1. <span data-ttu-id="73542-222">Выполните вход вашей Скайп для сервера переднего плана Business Server, с помощью Скайп для учетной записи администратора предприятия.</span><span class="sxs-lookup"><span data-stu-id="73542-222">Log in to your Skype for Business Server Front End server using a Skype for Business administrator account.</span></span>

2. <span data-ttu-id="73542-223">Запустите Скайп для консоли Business Server.</span><span class="sxs-lookup"><span data-stu-id="73542-223">Launch the Skype for Business Server Management Shell.</span></span>

3. <span data-ttu-id="73542-224">В Скайп для Business Server Командная консоль командной строки создайте новую конфигурацию веб-службы для каждого директора, корпоративного пула и сервера Standard Edition, который будет включен для пассивной проверки подлинности, выполнив следующую команду:</span><span class="sxs-lookup"><span data-stu-id="73542-224">From the Skype for Business Server Management Shell command-line, create a new Web Service configuration for each Director, Enterprise Pool, and Standard Edition server that will be enabled for passive authentication by running the following command:</span></span>

  ```
  New-CsWebServiceConfiguration -Identity "Service:WebServer:SfBPool01.contoso.com" -UseWsFedPassiveAuth $true -WsFedPassiveMetadataUri https://dc.contoso.com/federationmetadata/2007-06/federationmetadata.xml
  ```

    > [!CAUTION]
    > <span data-ttu-id="73542-p110">Значением полного доменного имени WsFedPassiveMetadataUri является имя службы федерации сервера AD FS 2.0. Значение имени службы федерации можно найти в консоли управления AD FS 2.0, щелкнув **Служба** в области навигации правой кнопкой мыши и затем выбрав **Изменить свойства службы федерации**.</span><span class="sxs-lookup"><span data-stu-id="73542-p110">The value for the WsFedPassiveMetadataUri FQDN is the Federation Service Name of your AD FS 2.0 server. The Federation Service Name value can be found in the AD FS 2.0 Management Console by right-clicking on **Service** from the navigation pane and then selecting **Edit Federation Service Properties**.</span></span>

4. <span data-ttu-id="73542-227">Проверьте правильность значений UseWsFedPassiveAuth и WsFedPassiveMetadataUri, выполнив следующую команду:</span><span class="sxs-lookup"><span data-stu-id="73542-227">Verify that the UseWsFedPassiveAuth and WsFedPassiveMetadataUri values were set correctly by running the following command:</span></span>

  ```
  Get-CsWebServiceConfiguration -identity "Service:WebServer:SfBPool01.contoso.com" | format-list UseWsFedPassiveAuth, WsFedPassiveMetadataUri
  ```

5. <span data-ttu-id="73542-228">Для клиентов пассивная проверка подлинности является наименее предпочтительным способом проверки подлинности WebTicket.</span><span class="sxs-lookup"><span data-stu-id="73542-228">For clients, Passive Authentication is the least preferred authentication method for webticket authentication.</span></span> <span data-ttu-id="73542-229">Для всех директоров (en), Enterprise пулов и серверов Standard Edition, которые будут использоваться для пассивной проверки подлинности других типов проверки подлинности, необходимо отключить в Скайп для бизнеса веб-служб, выполнив следующий командлет:</span><span class="sxs-lookup"><span data-stu-id="73542-229">For all Directors, Enterprise Pools, and Standard Edition servers that will be enabled for passive authentication, all other authentication types must be disabled in Skype for Business Web Services by running the following cmdlet:</span></span>

  ```
  Set-CsWebServiceConfiguration -Identity "Service:WebServer:SfBPool01.contoso.com" -UseCertificateAuth $false -UsePinAuth $false -UseWindowsAuth NONE
  ```

6. <span data-ttu-id="73542-230">Убедитесь в том, что все остальные типы проверки подлинности успешно отключены, выполнив следующую команду:</span><span class="sxs-lookup"><span data-stu-id="73542-230">Verify that all other authentication types have been successfully disabled by running the following cmdlet:</span></span>

  ```
  Get-CsWebServiceConfiguration -Identity "Service:WebServer:SfBPool01.contoso.com" | format-list UseCertificateAuth, UsePinAuth, UseWindowsAuth
  ```

### <a name="proxy-configuration"></a><span data-ttu-id="73542-231">Конфигурация прокси-сервера</span><span class="sxs-lookup"><span data-stu-id="73542-231">Proxy Configuration</span></span>

<span data-ttu-id="73542-232">При отключении проверки подлинности сертификата для бизнеса веб-служб для Скайп Скайп для клиента Business будет использовать менее предпочитаемый тип проверки подлинности, например Kerberos или NTLM, проходить проверку подлинности в службе регистратора.</span><span class="sxs-lookup"><span data-stu-id="73542-232">When certificate authentication is disabled for Skype for Business Web Services, the Skype for Business client will use a less preferred authentication type, such as Kerberos or NTLM, to authenticate to the Registrar service.</span></span> <span data-ttu-id="73542-233">Проверка подлинности по сертификату и в этом случае необходима для извлечения WebTicket клиентом, однако для службы регистратора необходимо отключить Kerberos и NTLM.</span><span class="sxs-lookup"><span data-stu-id="73542-233">Certificate authentication is still needed to allow the client to retrieve a webticket, however, Kerberos and NTLM must be disabled for the Registrar service.</span></span>

<span data-ttu-id="73542-234">Ниже описана процедура создания настраиваемой конфигурации прокси-сервера для пограничных пулов, корпоративных пулов и серверов Standard Edition, для которых будет включена пассивная проверка подлинности.</span><span class="sxs-lookup"><span data-stu-id="73542-234">The following steps describe how to create a custom proxy configuration for Edge Pools, Enterprise Pools, and Standard Edition servers that will be enabled for passive authentication.</span></span>

### <a name="to-create-a-custom-proxy-configuration"></a><span data-ttu-id="73542-235">Порядок создания настраиваемой конфигурации прокси-сервера</span><span class="sxs-lookup"><span data-stu-id="73542-235">To create a custom proxy configuration</span></span>

1. <span data-ttu-id="73542-236">В Скайп для Business Server Командная консоль командной строки создайте новую конфигурацию прокси-сервера для каждого Скайп для пограничного пула Business Server, корпоративный пул и Standard Edition server, который будет использоваться для пассивной проверки подлинности, выполнив следующие команды:</span><span class="sxs-lookup"><span data-stu-id="73542-236">From the Skype for Business Server Management Shell command-line, create a new proxy configuration for each Skype for Business Server Edge Pool, Enterprise Pool, and Standard Edition server that will be enabled for passive authentication by running the following commands:</span></span>

  ```
  New-CsProxyConfiguration -Identity "Service:EdgeServer:EdgePool01.contoso.com" -UseKerberosForClientToProxyAuth $False -UseNtlmForClientToProxyAuth $False
  ```

  ```
  New-CsProxyConfiguration -Identity "Service:Registrar:SfBPool01.contoso.com" -UseKerberosForClientToProxyAuth $False -UseNtlmForClientToProxyAuth $False
  ```

2. <span data-ttu-id="73542-237">Убедитесь, что все остальные типы проверки подлинности прокси-сервера успешно отключены, выполнив следующую команду:</span><span class="sxs-lookup"><span data-stu-id="73542-237">Verify that all other proxy authentication types have been successfully disabled by running the following command:</span></span>

  ```
  Get-CsProxyConfiguration -Identity "Service:Registrar:SfBPool01.contoso.com" | format-list UseKerberosForClientToProxyAuth, UseNtlmForClientToProxyAuth, UseCertifcateForClientToProxyAuth
  ```

## <a name="see-also"></a><span data-ttu-id="73542-238">См. также</span><span class="sxs-lookup"><span data-stu-id="73542-238">See also</span></span>

[<span data-ttu-id="73542-239">Управление двухфакторной проверки подлинности в Скайп для Business Server</span><span class="sxs-lookup"><span data-stu-id="73542-239">Manage two-factor authentication in Skype for Business Server</span></span>](two-factor-authentication.md)

[<span data-ttu-id="73542-240">Использовать двухфакторной проверки подлинности с помощью Скайп для бизнеса клиентов и Скайп для Business Server</span><span class="sxs-lookup"><span data-stu-id="73542-240">Use two-factor authentication with Skype for Business client and Skype for Business Server</span></span>](use.md)