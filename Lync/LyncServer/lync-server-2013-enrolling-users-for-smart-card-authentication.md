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
ms.openlocfilehash: cfbfcd73aba4079d74074adcd2710b8a2d45aeba
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48526776"
---
# <a name="enrolling-users-for-smart-card-authentication-in-lync-server-2013"></a><span data-ttu-id="36e5e-102">Регистрация пользователей для проверки подлинности с помощью смарт-карты в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="36e5e-102">Enrolling users for smart card authentication in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="36e5e-103">_**Последнее изменение темы:** 2013-07-03_</span><span class="sxs-lookup"><span data-stu-id="36e5e-103">_**Topic Last Modified:** 2013-07-03_</span></span>

<span data-ttu-id="36e5e-104">Существует два способа регистрации пользователей для проверки подлинности с помощью смарт-карты.</span><span class="sxs-lookup"><span data-stu-id="36e5e-104">There are generally two methods for enrolling users for smart card authentication.</span></span> <span data-ttu-id="36e5e-105">Более простой способ заключается в том, что пользователи регистрируются напрямую для проверки подлинности с помощью веб-карты с помощью веб-регистрации, а более сложный метод включает использование агента регистрации.</span><span class="sxs-lookup"><span data-stu-id="36e5e-105">The easier method involves having users enroll directly for smart card authentication using web enrollment, while the more complex method involves using an enrollment agent.</span></span> <span data-ttu-id="36e5e-106">В этом разделе рассматривается самостоятельная регистрация сертификатов смарт-карт.</span><span class="sxs-lookup"><span data-stu-id="36e5e-106">This topic focuses on self-enrollment for smartcard certificates.</span></span>

<span data-ttu-id="36e5e-107">Для получения дополнительных сведений о регистрации от имени пользователей в качестве агента регистрации обратитесь к разделу регистрация сертификатов от имени других пользователей [https://go.microsoft.com/fwlink/p/?LinkID=313367](https://go.microsoft.com/fwlink/p/?linkid=313367) .</span><span class="sxs-lookup"><span data-stu-id="36e5e-107">For more information on enrolling on behalf of users as an enrollment agent, see Enroll for Certificates on Behalf of Other Users at [https://go.microsoft.com/fwlink/p/?LinkID=313367](https://go.microsoft.com/fwlink/p/?linkid=313367).</span></span>

<div>

## <a name="to-enroll-users-for-smart-card-authentication"></a><span data-ttu-id="36e5e-108">Регистрация пользователей для проверки подлинности с помощью смарт-карты</span><span class="sxs-lookup"><span data-stu-id="36e5e-108">To Enroll Users for Smart Card Authentication</span></span>

1.  <span data-ttu-id="36e5e-109">Войдите на рабочую станцию Windows 8, используя учетные данные пользователя с включенной поддержкой Lync.</span><span class="sxs-lookup"><span data-stu-id="36e5e-109">Log in to the Windows 8 workstation using the credentials of a Lync-enabled user.</span></span>

2.  <span data-ttu-id="36e5e-110">Запустите Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="36e5e-110">Launch Internet Explorer.</span></span>

3.  <span data-ttu-id="36e5e-111">Перейдите на страницу **веб-регистрации центра сертификации** ( https://MyCA.contoso.com/certsrv) например,</span><span class="sxs-lookup"><span data-stu-id="36e5e-111">Browse to the **Certificate Authority Web Enrollment** page (e.g. https://MyCA.contoso.com/certsrv).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="36e5e-112">Если вы используете Internet Explorer 10, вам может потребоваться просмотреть этот веб-сайт в режиме совместимости.</span><span class="sxs-lookup"><span data-stu-id="36e5e-112">If you are using Internet Explorer 10, you may need to view this website in Compatibility Mode.</span></span>

    
    </div>

4.  <span data-ttu-id="36e5e-113">На странице **приветствия** выберите **запросить сертификат**.</span><span class="sxs-lookup"><span data-stu-id="36e5e-113">On the **Welcome** Page, select **Request a certificate**.</span></span>

5.  <span data-ttu-id="36e5e-114">Затем выберите **Расширенный запрос**.</span><span class="sxs-lookup"><span data-stu-id="36e5e-114">Next, select **Advanced Request**.</span></span>

6.  <span data-ttu-id="36e5e-115">Выберите **создать и отправить запрос к этому ЦС**.</span><span class="sxs-lookup"><span data-stu-id="36e5e-115">Select **Create and submit a request to this CA**.</span></span>

7.  <span data-ttu-id="36e5e-116">В разделе **шаблон сертификата** выберите **пользователь смарт-карты** и выполните Расширенный запрос сертификата со следующими значениями:</span><span class="sxs-lookup"><span data-stu-id="36e5e-116">Select **Smartcard User** under the **Certificate Template** section and complete the advanced certificate request with the following values:</span></span>
    
      - <span data-ttu-id="36e5e-117">**Ключевые параметры** подтвердит, что он имеет следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="36e5e-117">**Key Options** confirm he following settings:</span></span>
        
          - <span data-ttu-id="36e5e-118">Выберите переключатель **создать новый набор ключей**</span><span class="sxs-lookup"><span data-stu-id="36e5e-118">Select the **Create new key set** radio button</span></span>
        
          - <span data-ttu-id="36e5e-119">Для поставщика **служб шифрования**выберите **базовый поставщик криптографии смарт-карт (Майкрософт** )</span><span class="sxs-lookup"><span data-stu-id="36e5e-119">For **CSP**, select **Microsoft Base Smart Card Crypto Provider**</span></span>
        
          - <span data-ttu-id="36e5e-120">В **разделе Использование ключа**выберите **Exchange** (единственный доступный вариант).</span><span class="sxs-lookup"><span data-stu-id="36e5e-120">For **Key Usage**, select **Exchange** (this is the only option available).</span></span>
        
          - <span data-ttu-id="36e5e-121">В поле **Размер ключа**введите **2048**</span><span class="sxs-lookup"><span data-stu-id="36e5e-121">For **Key Size**, enter **2048**</span></span>
        
          - <span data-ttu-id="36e5e-122">Убедитесь, что выбрано **Автоматическое имя контейнера ключей**</span><span class="sxs-lookup"><span data-stu-id="36e5e-122">Confirm that **Automatic key container name** is selected</span></span>
        
          - <span data-ttu-id="36e5e-123">Не снимайте остальные флажки.</span><span class="sxs-lookup"><span data-stu-id="36e5e-123">Leave the other boxes unchecked.</span></span>
    
      - <span data-ttu-id="36e5e-124">В разделе **Дополнительные параметры** подтвердите указанные ниже значения.</span><span class="sxs-lookup"><span data-stu-id="36e5e-124">Under **Additional Options** confirm the following values:</span></span>
        
          - <span data-ttu-id="36e5e-125">В **формате запроса** выберите **CMC**.</span><span class="sxs-lookup"><span data-stu-id="36e5e-125">For **Request Format** select **CMC**.</span></span>
        
          - <span data-ttu-id="36e5e-126">Для **алгоритма хеширования** выберите **SHA1**.</span><span class="sxs-lookup"><span data-stu-id="36e5e-126">For **Hash Algorithm** select **sha1**.</span></span>
        
          - <span data-ttu-id="36e5e-127">В качестве **понятного имени** введите **смардкард Certificate**.</span><span class="sxs-lookup"><span data-stu-id="36e5e-127">For **Friendly Name** enter **Smardcard Certificate**.</span></span>

8.  <span data-ttu-id="36e5e-128">Если вы используете физическое устройство чтения смарт-карт, вставьте его в устройство.</span><span class="sxs-lookup"><span data-stu-id="36e5e-128">If you are using a physical smartcard reader, insert the smart card into the device.</span></span>

9.  <span data-ttu-id="36e5e-129">Нажмите кнопку **Отправить** , чтобы отправить запрос на сертификат.</span><span class="sxs-lookup"><span data-stu-id="36e5e-129">Click **Submit** to submit the certificate request.</span></span>

10. <span data-ttu-id="36e5e-130">При появлении соответствующего запроса введите ПИН-код, который использовался для создания виртуальной смарт-карты.</span><span class="sxs-lookup"><span data-stu-id="36e5e-130">When prompted, enter the PIN that was used to create the virtual smart card.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="36e5e-131">Значение ПИН-кода виртуальной смарт-карты по умолчанию: "12345678".</span><span class="sxs-lookup"><span data-stu-id="36e5e-131">The default virtual smart card PIN value is ‘12345678’.</span></span>

    
    </div>

11. <span data-ttu-id="36e5e-132">После выдачи сертификата щелкните **установить этот сертификат** для завершения процедуры регистрации.</span><span class="sxs-lookup"><span data-stu-id="36e5e-132">Once the certificate has been issued, click **Install this certificate** to complete the enrollment process.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="36e5e-133">Если запрос на сертификат завершается с ошибкой "Этот веб-браузер не поддерживает создание запросов на сертификат", существует три способа решения этой проблемы:</span><span class="sxs-lookup"><span data-stu-id="36e5e-133">If your certificate request fails with the error “This Web browser does not support the generation of certificate requests,” there are three possible ways to resolve the issue:</span></span> 
    > <OL>
    > <LI>
    > <P><span data-ttu-id="36e5e-134">Включение режима совместимости в Internet Explorer</span><span class="sxs-lookup"><span data-stu-id="36e5e-134">Enable Compatibility View in Internet Explorer</span></span></P>
    > <LI>
    > <P><span data-ttu-id="36e5e-135">Включение параметра "включить параметры интрасети" в Internet Explorer</span><span class="sxs-lookup"><span data-stu-id="36e5e-135">Enable the Turn on Intranet settings option in Internet Explorer</span></span></P>
    > <LI>
    > <P><span data-ttu-id="36e5e-136">Установите флажок Сбросить все зоны на уровень по умолчанию на вкладке Безопасность в меню Параметры Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="36e5e-136">Select the Reset all zones to default level setting under the Security tab in the Internet Explorer options menu.</span></span></P></LI></OL>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

