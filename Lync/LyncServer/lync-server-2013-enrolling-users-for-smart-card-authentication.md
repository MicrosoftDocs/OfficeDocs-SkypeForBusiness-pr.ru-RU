---
title: 'Lync Server 2013: регистрация пользователей для проверки подлинности с помощью смарт-карты'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enrolling users for smart card authentication
ms:assetid: a6445a83-a94b-423f-ba2a-12b5f84c5d75
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn308570(v=OCS.15)
ms:contentKeyID: 54973691
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 750e77b342b48d2c81bf05e160779ca5566f5a2f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41735449"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enrolling-users-for-smart-card-authentication-in-lync-server-2013"></a><span data-ttu-id="eef34-102">Регистрация пользователей для проверки подлинности с помощью смарт-карты в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="eef34-102">Enrolling users for smart card authentication in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="eef34-103">_**Тема последнего изменения:** 2013-07-03_</span><span class="sxs-lookup"><span data-stu-id="eef34-103">_**Topic Last Modified:** 2013-07-03_</span></span>

<span data-ttu-id="eef34-p101">Зарегистрировать пользователей для проверки подлинности с помощью смарт-карты можно двумя способами. Простой вариант — поручить пользователям самостоятельно зарегистрироваться с помощью функции регистрации через Интернет, в то время как сложный связан с использованием агента регистрации. В этом разделе рассматривается процедура самостоятельной регистрации для использования сертификатов смарт-карт.</span><span class="sxs-lookup"><span data-stu-id="eef34-p101">There are generally two methods for enrolling users for smart card authentication. The easier method involves having users enroll directly for smart card authentication using web enrollment, while the more complex method involves using an enrollment agent. This topic focuses on self-enrollment for smartcard certificates.</span></span>

<span data-ttu-id="eef34-107">Дополнительные сведения о регистрации от имени пользователей в качестве агента регистрации можно найти в разделе Регистрация сертификатов от имени других пользователей [http://go.microsoft.com/fwlink/p/?LinkID=313367](http://go.microsoft.com/fwlink/p/?linkid=313367).</span><span class="sxs-lookup"><span data-stu-id="eef34-107">For more information on enrolling on behalf of users as an enrollment agent, see Enroll for Certificates on Behalf of Other Users at [http://go.microsoft.com/fwlink/p/?LinkID=313367](http://go.microsoft.com/fwlink/p/?linkid=313367).</span></span>

<div>

## <a name="to-enroll-users-for-smart-card-authentication"></a><span data-ttu-id="eef34-108">Порядок регистрации пользователей для проверки подлинности с помощью смарт-карты</span><span class="sxs-lookup"><span data-stu-id="eef34-108">To Enroll Users for Smart Card Authentication</span></span>

1.  <span data-ttu-id="eef34-109">Войдите на рабочую станцию Windows 8, используя учетные данные пользователя с поддержкой Lync.</span><span class="sxs-lookup"><span data-stu-id="eef34-109">Log in to the Windows 8 workstation using the credentials of a Lync-enabled user.</span></span>

2.  <span data-ttu-id="eef34-110">Запустите браузер Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="eef34-110">Launch Internet Explorer.</span></span>

3.  <span data-ttu-id="eef34-111">Перейдите на страницу **веб-регистрации центра сертификации** (например https://MyCA.contoso.com/certsrv),</span><span class="sxs-lookup"><span data-stu-id="eef34-111">Browse to the **Certificate Authority Web Enrollment** page (e.g. https://MyCA.contoso.com/certsrv).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="eef34-112">В браузере Internet Explorer 10 эту страницу, возможно, потребуется открыть в режиме совместимости.</span><span class="sxs-lookup"><span data-stu-id="eef34-112">If you are using Internet Explorer 10, you may need to view this website in Compatibility Mode.</span></span>

    
    </div>

4.  <span data-ttu-id="eef34-113">На странице **приветствия** выберите **Запросить сертификат**.</span><span class="sxs-lookup"><span data-stu-id="eef34-113">On the **Welcome** Page, select **Request a certificate**.</span></span>

5.  <span data-ttu-id="eef34-114">Затем выберите **Расширенный запрос**.</span><span class="sxs-lookup"><span data-stu-id="eef34-114">Next, select **Advanced Request**.</span></span>

6.  <span data-ttu-id="eef34-115">Выберите **Создать и выдать запрос к этому ЦС**.</span><span class="sxs-lookup"><span data-stu-id="eef34-115">Select **Create and submit a request to this CA**.</span></span>

7.  <span data-ttu-id="eef34-116">В разделе **Шаблон сертификата** выберите **Пользователь смарт-карты** и введите в полях расширенного запроса сертификата следующие значения.</span><span class="sxs-lookup"><span data-stu-id="eef34-116">Select **Smartcard User** under the **Certificate Template** section and complete the advanced certificate request with the following values:</span></span>
    
      - <span data-ttu-id="eef34-117">В разделе **Параметры ключа** задайте следующие значения.</span><span class="sxs-lookup"><span data-stu-id="eef34-117">**Key Options** confirm he following settings:</span></span>
        
          - <span data-ttu-id="eef34-118">Установите переключатель в положение **Создать новый набор ключей**.</span><span class="sxs-lookup"><span data-stu-id="eef34-118">Select the **Create new key set** radio button</span></span>
        
          - <span data-ttu-id="eef34-119">Для параметра **Поставщик служб шифрования** выберите значение **Базовый поставщик криптографии смарт-карт (Microsoft)**.</span><span class="sxs-lookup"><span data-stu-id="eef34-119">For **CSP**, select **Microsoft Base Smart Card Crypto Provider**</span></span>
        
          - <span data-ttu-id="eef34-120">Для параметра **Использование ключа** выберите значение **Обмен** (единственное доступное значение).</span><span class="sxs-lookup"><span data-stu-id="eef34-120">For **Key Usage**, select **Exchange** (this is the only option available).</span></span>
        
          - <span data-ttu-id="eef34-121">В поле **Размер ключа** введите значение **2048**.</span><span class="sxs-lookup"><span data-stu-id="eef34-121">For **Key Size**, enter **2048**</span></span>
        
          - <span data-ttu-id="eef34-122">Убедитесь в том, что флажок **Автоматическое имя контейнера ключа** установлен.</span><span class="sxs-lookup"><span data-stu-id="eef34-122">Confirm that **Automatic key container name** is selected</span></span>
        
          - <span data-ttu-id="eef34-123">Оставьте остальные флажки снятыми.</span><span class="sxs-lookup"><span data-stu-id="eef34-123">Leave the other boxes unchecked.</span></span>
    
      - <span data-ttu-id="eef34-124">В разделе **Дополнительные параметры** задайте следующие значения.</span><span class="sxs-lookup"><span data-stu-id="eef34-124">Under **Additional Options** confirm the following values:</span></span>
        
          - <span data-ttu-id="eef34-125">Для параметра **Формат запроса** выберите значение **CMC**.</span><span class="sxs-lookup"><span data-stu-id="eef34-125">For **Request Format** select **CMC**.</span></span>
        
          - <span data-ttu-id="eef34-126">Для параметра **Алгоритм хэширования** выберите значение **sha1**.</span><span class="sxs-lookup"><span data-stu-id="eef34-126">For **Hash Algorithm** select **sha1**.</span></span>
        
          - <span data-ttu-id="eef34-127">В поле **Понятное имя** введите значение **Smardcard Certificate**.</span><span class="sxs-lookup"><span data-stu-id="eef34-127">For **Friendly Name** enter **Smardcard Certificate**.</span></span>

8.  <span data-ttu-id="eef34-128">Если используется физическое устройство считывания смарт-карт, вставьте смарт-карту в устройство.</span><span class="sxs-lookup"><span data-stu-id="eef34-128">If you are using a physical smartcard reader, insert the smart card into the device.</span></span>

9.  <span data-ttu-id="eef34-129">Нажмите кнопку **Отправить** для отправки запроса сертификата.</span><span class="sxs-lookup"><span data-stu-id="eef34-129">Click **Submit** to submit the certificate request.</span></span>

10. <span data-ttu-id="eef34-130">Когда будет предложено, введите ПИН-код, использовавшийся при создании виртуальной смарт-карты.</span><span class="sxs-lookup"><span data-stu-id="eef34-130">When prompted, enter the PIN that was used to create the virtual smart card.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="eef34-131">Значение ПИН-кода виртуальной смарт-карты по умолчанию — 12345678.</span><span class="sxs-lookup"><span data-stu-id="eef34-131">The default virtual smart card PIN value is ‘12345678’.</span></span>

    
    </div>

11. <span data-ttu-id="eef34-132">После выдачи сертификата щелкните **Установить этот сертификат** для завершения процедуры регистрации.</span><span class="sxs-lookup"><span data-stu-id="eef34-132">Once the certificate has been issued, click **Install this certificate** to complete the enrollment process.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="eef34-133">Если запрос на получение сертификата завершается неудачей с ошибкой "Этот веб-браузер не поддерживает создание запросов на сертификат", устранить эту ошибку можно тремя способами.</span><span class="sxs-lookup"><span data-stu-id="eef34-133">If your certificate request fails with the error “This Web browser does not support the generation of certificate requests,” there are three possible ways to resolve the issue:</span></span> 
    > <OL>
    > <LI>
    > <P><span data-ttu-id="eef34-134">Включите режим совместимости в браузере Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="eef34-134">Enable Compatibility View in Internet Explorer</span></span></P>
    > <LI>
    > <P><span data-ttu-id="eef34-135">Включите параметр "Включить параметры интрасети" в браузере Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="eef34-135">Enable the Turn on Intranet settings option in Internet Explorer</span></span></P>
    > <LI>
    > <P><span data-ttu-id="eef34-136">Выберите параметр "Выбрать уровень безопасности по умолчанию для всех зон" на вкладке "Безопасность" в меню параметров Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="eef34-136">Select the Reset all zones to default level setting under the Security tab in the Internet Explorer options menu.</span></span></P></LI></OL>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

