---
title: 'Lync Server 2013: регистрация пользователей для проверки подлинности с помощью смарт-карты'
description: 'Lync Server 2013: регистрация пользователей для проверки подлинности с помощью смарт-карты.'
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
ms.openlocfilehash: 9d67994d2152ac344934d093a1b6f7d482a7933a
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48558475"
---
# <a name="enrolling-users-for-smart-card-authentication-in-lync-server-2013"></a><span data-ttu-id="b77a9-103">Регистрация пользователей для проверки подлинности с помощью смарт-карты в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b77a9-103">Enrolling users for smart card authentication in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b77a9-104">_**Последнее изменение темы:** 2013-07-03_</span><span class="sxs-lookup"><span data-stu-id="b77a9-104">_**Topic Last Modified:** 2013-07-03_</span></span>

<span data-ttu-id="b77a9-105">Существует два способа регистрации пользователей для проверки подлинности с помощью смарт-карты.</span><span class="sxs-lookup"><span data-stu-id="b77a9-105">There are generally two methods for enrolling users for smart card authentication.</span></span> <span data-ttu-id="b77a9-106">Более простой способ заключается в том, что пользователи регистрируются напрямую для проверки подлинности с помощью веб-карты с помощью веб-регистрации, а более сложный метод включает использование агента регистрации.</span><span class="sxs-lookup"><span data-stu-id="b77a9-106">The easier method involves having users enroll directly for smart card authentication using web enrollment, while the more complex method involves using an enrollment agent.</span></span> <span data-ttu-id="b77a9-107">В этом разделе рассматривается самостоятельная регистрация сертификатов смарт-карт.</span><span class="sxs-lookup"><span data-stu-id="b77a9-107">This topic focuses on self-enrollment for smartcard certificates.</span></span>

<span data-ttu-id="b77a9-108">Для получения дополнительных сведений о регистрации от имени пользователей в качестве агента регистрации обратитесь к разделу регистрация сертификатов от имени других пользователей [https://go.microsoft.com/fwlink/p/?LinkID=313367](https://go.microsoft.com/fwlink/p/?linkid=313367) .</span><span class="sxs-lookup"><span data-stu-id="b77a9-108">For more information on enrolling on behalf of users as an enrollment agent, see Enroll for Certificates on Behalf of Other Users at [https://go.microsoft.com/fwlink/p/?LinkID=313367](https://go.microsoft.com/fwlink/p/?linkid=313367).</span></span>

<div>

## <a name="to-enroll-users-for-smart-card-authentication"></a><span data-ttu-id="b77a9-109">Регистрация пользователей для проверки подлинности с помощью смарт-карты</span><span class="sxs-lookup"><span data-stu-id="b77a9-109">To Enroll Users for Smart Card Authentication</span></span>

1.  <span data-ttu-id="b77a9-110">Войдите на рабочую станцию Windows 8, используя учетные данные пользователя с включенной поддержкой Lync.</span><span class="sxs-lookup"><span data-stu-id="b77a9-110">Log in to the Windows 8 workstation using the credentials of a Lync-enabled user.</span></span>

2.  <span data-ttu-id="b77a9-111">Запустите Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="b77a9-111">Launch Internet Explorer.</span></span>

3.  <span data-ttu-id="b77a9-112">Перейдите на страницу **веб-регистрации центра сертификации** ( https://MyCA.contoso.com/certsrv) например,</span><span class="sxs-lookup"><span data-stu-id="b77a9-112">Browse to the **Certificate Authority Web Enrollment** page (e.g. https://MyCA.contoso.com/certsrv).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="b77a9-113">Если вы используете Internet Explorer 10, вам может потребоваться просмотреть этот веб-сайт в режиме совместимости.</span><span class="sxs-lookup"><span data-stu-id="b77a9-113">If you are using Internet Explorer 10, you may need to view this website in Compatibility Mode.</span></span>

    
    </div>

4.  <span data-ttu-id="b77a9-114">На странице **приветствия** выберите **запросить сертификат**.</span><span class="sxs-lookup"><span data-stu-id="b77a9-114">On the **Welcome** Page, select **Request a certificate**.</span></span>

5.  <span data-ttu-id="b77a9-115">Затем выберите **Расширенный запрос**.</span><span class="sxs-lookup"><span data-stu-id="b77a9-115">Next, select **Advanced Request**.</span></span>

6.  <span data-ttu-id="b77a9-116">Выберите **создать и отправить запрос к этому ЦС**.</span><span class="sxs-lookup"><span data-stu-id="b77a9-116">Select **Create and submit a request to this CA**.</span></span>

7.  <span data-ttu-id="b77a9-117">В разделе **шаблон сертификата** выберите **пользователь смарт-карты** и выполните Расширенный запрос сертификата со следующими значениями:</span><span class="sxs-lookup"><span data-stu-id="b77a9-117">Select **Smartcard User** under the **Certificate Template** section and complete the advanced certificate request with the following values:</span></span>
    
      - <span data-ttu-id="b77a9-118">**Ключевые параметры** подтвердит, что он имеет следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="b77a9-118">**Key Options** confirm he following settings:</span></span>
        
          - <span data-ttu-id="b77a9-119">Выберите переключатель **создать новый набор ключей**</span><span class="sxs-lookup"><span data-stu-id="b77a9-119">Select the **Create new key set** radio button</span></span>
        
          - <span data-ttu-id="b77a9-120">Для поставщика **служб шифрования**выберите **базовый поставщик криптографии смарт-карт (Майкрософт** )</span><span class="sxs-lookup"><span data-stu-id="b77a9-120">For **CSP**, select **Microsoft Base Smart Card Crypto Provider**</span></span>
        
          - <span data-ttu-id="b77a9-121">В **разделе Использование ключа**выберите **Exchange** (единственный доступный вариант).</span><span class="sxs-lookup"><span data-stu-id="b77a9-121">For **Key Usage**, select **Exchange** (this is the only option available).</span></span>
        
          - <span data-ttu-id="b77a9-122">В поле **Размер ключа**введите **2048**</span><span class="sxs-lookup"><span data-stu-id="b77a9-122">For **Key Size**, enter **2048**</span></span>
        
          - <span data-ttu-id="b77a9-123">Убедитесь, что выбрано **Автоматическое имя контейнера ключей**</span><span class="sxs-lookup"><span data-stu-id="b77a9-123">Confirm that **Automatic key container name** is selected</span></span>
        
          - <span data-ttu-id="b77a9-124">Не снимайте остальные флажки.</span><span class="sxs-lookup"><span data-stu-id="b77a9-124">Leave the other boxes unchecked.</span></span>
    
      - <span data-ttu-id="b77a9-125">В разделе **Дополнительные параметры** подтвердите указанные ниже значения.</span><span class="sxs-lookup"><span data-stu-id="b77a9-125">Under **Additional Options** confirm the following values:</span></span>
        
          - <span data-ttu-id="b77a9-126">В **формате запроса** выберите **CMC**.</span><span class="sxs-lookup"><span data-stu-id="b77a9-126">For **Request Format** select **CMC**.</span></span>
        
          - <span data-ttu-id="b77a9-127">Для **алгоритма хеширования** выберите **SHA1**.</span><span class="sxs-lookup"><span data-stu-id="b77a9-127">For **Hash Algorithm** select **sha1**.</span></span>
        
          - <span data-ttu-id="b77a9-128">В качестве **понятного имени** введите **смардкард Certificate**.</span><span class="sxs-lookup"><span data-stu-id="b77a9-128">For **Friendly Name** enter **Smardcard Certificate**.</span></span>

8.  <span data-ttu-id="b77a9-129">Если вы используете физическое устройство чтения смарт-карт, вставьте его в устройство.</span><span class="sxs-lookup"><span data-stu-id="b77a9-129">If you are using a physical smartcard reader, insert the smart card into the device.</span></span>

9.  <span data-ttu-id="b77a9-130">Нажмите кнопку **Отправить** , чтобы отправить запрос на сертификат.</span><span class="sxs-lookup"><span data-stu-id="b77a9-130">Click **Submit** to submit the certificate request.</span></span>

10. <span data-ttu-id="b77a9-131">При появлении соответствующего запроса введите ПИН-код, который использовался для создания виртуальной смарт-карты.</span><span class="sxs-lookup"><span data-stu-id="b77a9-131">When prompted, enter the PIN that was used to create the virtual smart card.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="b77a9-132">Значение ПИН-кода виртуальной смарт-карты по умолчанию: "12345678".</span><span class="sxs-lookup"><span data-stu-id="b77a9-132">The default virtual smart card PIN value is ‘12345678’.</span></span>

    
    </div>

11. <span data-ttu-id="b77a9-133">После выдачи сертификата щелкните **установить этот сертификат** для завершения процедуры регистрации.</span><span class="sxs-lookup"><span data-stu-id="b77a9-133">Once the certificate has been issued, click **Install this certificate** to complete the enrollment process.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="b77a9-134">Если запрос на сертификат завершается с ошибкой "Этот веб-браузер не поддерживает создание запросов на сертификат", существует три способа решения этой проблемы:</span><span class="sxs-lookup"><span data-stu-id="b77a9-134">If your certificate request fails with the error “This Web browser does not support the generation of certificate requests,” there are three possible ways to resolve the issue:</span></span> 
    > <OL>
    > <LI>
    > <P><span data-ttu-id="b77a9-135">Включение режима совместимости в Internet Explorer</span><span class="sxs-lookup"><span data-stu-id="b77a9-135">Enable Compatibility View in Internet Explorer</span></span></P>
    > <LI>
    > <P><span data-ttu-id="b77a9-136">Включение параметра "включить параметры интрасети" в Internet Explorer</span><span class="sxs-lookup"><span data-stu-id="b77a9-136">Enable the Turn on Intranet settings option in Internet Explorer</span></span></P>
    > <LI>
    > <P><span data-ttu-id="b77a9-137">Установите флажок Сбросить все зоны на уровень по умолчанию на вкладке Безопасность в меню Параметры Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="b77a9-137">Select the Reset all zones to default level setting under the Security tab in the Internet Explorer options menu.</span></span></P></LI></OL>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

