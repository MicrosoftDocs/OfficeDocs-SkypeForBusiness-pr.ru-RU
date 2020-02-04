---
title: 'Lync Server 2013: настройка сертификатов для директора'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure certificates for the Director
ms:assetid: 22988186-15ae-43b1-92f4-0adb3b75a7fd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398296(v=OCS.15)
ms:contentKeyID: 48183612
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fccab201ee9ab16b0195bc2780c37ab85f0519e9
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739389"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-certificates-for-the-director-in-lync-server-2013"></a><span data-ttu-id="0146d-102">Настройка сертификатов для директора в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0146d-102">Configure certificates for the Director in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0146d-103">_**Тема последнего изменения:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="0146d-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="0146d-104">При запуске мастера сертификатов убедитесь, что вы вошли в систему под учетной записью, которая является членом группы, которой назначены соответствующие разрешения для типа шаблона сертификата, который вы будете использовать.</span><span class="sxs-lookup"><span data-stu-id="0146d-104">When you run the Certificate Wizard, ensure that you are logged in using an account that is a member of a group that has been assigned the appropriate permissions for the type of certificate template you will use.</span></span> <span data-ttu-id="0146d-105">По умолчанию запрос сертификата Lync Server 2013 будет использовать шаблон сертификата веб-сервера.</span><span class="sxs-lookup"><span data-stu-id="0146d-105">By default, a Lync Server 2013 certificate request will use the Web Server certificate template.</span></span> <span data-ttu-id="0146d-106">Если вы используете учетную запись, которая входит в группу Рткуниверсалсерверадминс, чтобы запросить сертификат с помощью этого шаблона, убедитесь, что группе назначены разрешения, необходимые для использования этого шаблона.</span><span class="sxs-lookup"><span data-stu-id="0146d-106">If you use an account that is a member of the RTCUniversalServerAdmins group to request a certificate using this template, verify that the group has been assigned the Enroll permissions required to use that template.</span></span>



</div>

<span data-ttu-id="0146d-107">Для каждого режиссера требуется сертификат по умолчанию, внутренний веб-сертификат и внешний сертификат на веб-сайте.</span><span class="sxs-lookup"><span data-stu-id="0146d-107">Each Director requires a default certificate, a web internal certificate, and a web external certificate.</span></span> <span data-ttu-id="0146d-108">Сведения о требованиях к сертификатам для режиссеров приведены в разделе [требования к сертификатам внутренних серверов в Lync Server 2013](lync-server-2013-certificate-requirements-for-internal-servers.md) в документации по планированию.</span><span class="sxs-lookup"><span data-stu-id="0146d-108">For details about the certificate requirements for Directors, see [Certificate requirements for internal servers in Lync Server 2013](lync-server-2013-certificate-requirements-for-internal-servers.md) in the Planning documentation.</span></span>

<span data-ttu-id="0146d-109">Для настройки сертификатов режиссера выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="0146d-109">Use the following procedure to configure Director certificates.</span></span> <span data-ttu-id="0146d-110">Повторите эти действия для каждого директора.</span><span class="sxs-lookup"><span data-stu-id="0146d-110">Repeat the procedure for each Director.</span></span> <span data-ttu-id="0146d-111">Действия, описанные в этой статье, описаны для настройки сертификата из внутреннего корневого центра сертификации (ЦС) предприятия, развернутого в вашей организации и с помощью обработки запросов в автономном режиме.</span><span class="sxs-lookup"><span data-stu-id="0146d-111">The steps of this procedure describe how to configure a certificate from an Internal Enterprise Root certification authority (CA) deployed by your organization and with offline request processing.</span></span> <span data-ttu-id="0146d-112">Чтобы узнать больше о получении сертификатов из внешнего ЦС, обратитесь в службу поддержки.</span><span class="sxs-lookup"><span data-stu-id="0146d-112">For details about obtaining certificates from an external CA, contact your support team.</span></span>

<div>

## <a name="to-configure-certificates-for-the-director-or-director-pool"></a><span data-ttu-id="0146d-113">Настройка сертификатов для режиссера или пула</span><span class="sxs-lookup"><span data-stu-id="0146d-113">To configure certificates for the Director or Director pool</span></span>

1.  <span data-ttu-id="0146d-114">В мастере развертывания Lync Server рядом с **шагом 3: запрос, установка и назначение сертификатов**нажмите кнопку **выполнить**.</span><span class="sxs-lookup"><span data-stu-id="0146d-114">In the Lync Server Deployment Wizard, next to **Step 3: Request, Install or Assign Certificates**, click **Run**.</span></span>

2.  <span data-ttu-id="0146d-115">На странице **Мастер сертификатов** щелкните элемент **Запросить**.</span><span class="sxs-lookup"><span data-stu-id="0146d-115">On the **Certificate Wizard** page, click **Request**.</span></span>

3.  <span data-ttu-id="0146d-116">На странице **запроса сертификата** нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="0146d-116">On the **Certificate Request** page, click **Next**.</span></span>

4.  <span data-ttu-id="0146d-117">На странице **отложенные или немедленные запросы** подтвердите **отправку запроса по умолчанию в режим онлайнового центра сертификации** и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="0146d-117">On the **Delayed or Immediate Requests** page, accept the default **Send the request immediately to an online certification authority** option, and then click **Next**.</span></span>

5.  <span data-ttu-id="0146d-118">На странице **выберите центр сертификации (ЦС)** выберите внутренний центр сертификации Windows, который вы хотите использовать, и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="0146d-118">On the **Choose a Certification Authority (CA)** page, click the internal Windows certification authority that you want to use, and then click **Next**.</span></span>

6.  <span data-ttu-id="0146d-119">На странице **учетной записи центра сертификации** укажите альтернативные учетные данные, которые будут использоваться, если у учетной записи, с которой вы вошли в систему, нет достаточных полномочий для запроса сертификата, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="0146d-119">On the **Certification Authority Account** page, specify alternate credentials to be used if the account you are logged on with does not have sufficient authority to request the certificate, and then click **Next**.</span></span>

7.  <span data-ttu-id="0146d-120">На странице **Укажите другой шаблон сертификата** нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="0146d-120">On the **Specify Alternate Certificate Template** page, click **Next**.</span></span>

8.  <span data-ttu-id="0146d-121">На странице **имя и параметры безопасности** можно указать **понятное имя**, присвоить 2048-разрядную длину ключа, а затем нажать кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="0146d-121">On the **Name and Security Settings** page, you can specify a **Friendly Name**, accept the 2048-bit key length, and then click **Next**.</span></span>

9.  <span data-ttu-id="0146d-122">На странице **сведения об организации** , при необходимости укажите сведения об организации, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="0146d-122">On the **Organization Information** page, optionally specify organization information, and then click **Next**.</span></span>

10. <span data-ttu-id="0146d-123">На странице **сведения о географическом** расположении, при необходимости укажите сведения о местоположении, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="0146d-123">On the **Geographical Information** page, optionally specify geographical information, and then click **Next**.</span></span>

11. <span data-ttu-id="0146d-124">На странице **имя субъекта/дополнительные имена субъектов** нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="0146d-124">On the **Subject Name / Subject Alternative Names** page, click **Next**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="0146d-125">Список альтернативных имен субъектов должен содержать имя компьютера, на котором устанавливается режиссер (если это один руководитель) или имя пула, и простые URL-имена, настроенные для Организации.</span><span class="sxs-lookup"><span data-stu-id="0146d-125">The subject alternative name list should contain the name of the computer on which you are installing the Director (if a single Director) or the Director pool name, and the simple URL names configured for the organization.</span></span>

    
    </div>

12. <span data-ttu-id="0146d-126">На странице **Параметры домена SIP в разделе "альтернативные имена субъектов" (SAN)** выберите **настроенные домены SIP** для всех доменов, которые должны обрабатываться режиссером, и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="0146d-126">On the **SIP Domain Setting on Subject Alternate Names (SANs)** page, select the **Configured SIP Domains** for all domains that you want the Director to handle, and then click **Next**.</span></span>

13. <span data-ttu-id="0146d-127">На странице **Настройте дополнительные имена тем** добавьте дополнительные дополнительные имена тем, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="0146d-127">On the **Configure Additional Subject Alternative Names** page, add any additional required subject alternative names, and then click **Next**.</span></span>

14. <span data-ttu-id="0146d-128">На странице **Сводка запроса на сертификат** нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="0146d-128">On the **Certificate Request Summary** page, click **Next**.</span></span>

15. <span data-ttu-id="0146d-129">На странице **выполнение команд** нажмите кнопку **Далее** после завершения выполнения команд.</span><span class="sxs-lookup"><span data-stu-id="0146d-129">On the **Executing Commands** page, click **Next** after the commands have finished running.</span></span>

16. <span data-ttu-id="0146d-130">На странице **состояния запроса онлайнового сертификата** нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="0146d-130">On the **Online Certificate Request Status** page, click **Finish**.</span></span>

17. <span data-ttu-id="0146d-131">На странице " **назначение сертификата** " нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="0146d-131">On the **Certificate Assignment** page, click **Next**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="0146d-132">Если вы хотите просмотреть сертификат, дважды щелкните его в списке.</span><span class="sxs-lookup"><span data-stu-id="0146d-132">if you want to view the certificate, double-click the certificate in the list.</span></span>

    
    </div>

18. <span data-ttu-id="0146d-133">На странице **Сводка о назначениях сертификатов** нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="0146d-133">On the **Certificate Assignment Summary** page, click **Next**.</span></span>

19. <span data-ttu-id="0146d-134">На странице **выполнение команд** нажмите кнопку **Готово** после завершения выполнения команд.</span><span class="sxs-lookup"><span data-stu-id="0146d-134">On the **Executing Commands** page, click **Finish** after the commands have finished running.</span></span>

20. <span data-ttu-id="0146d-135">На странице **мастера сертификатов** нажмите кнопку **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="0146d-135">On the **Certificate Wizard** page, click **Close**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

