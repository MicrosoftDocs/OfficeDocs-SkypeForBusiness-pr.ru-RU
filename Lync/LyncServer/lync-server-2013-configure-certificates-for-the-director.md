---
title: 'Lync Server 2013: Настройка сертификатов для директора'
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
ms.openlocfilehash: 7c5fef23ca24d9a09d326b75ec2ad2e30704852f
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42205101"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-certificates-for-the-director-in-lync-server-2013"></a><span data-ttu-id="d343d-102">Настройка сертификатов для директора в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d343d-102">Configure certificates for the Director in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d343d-103">_**Последнее изменение темы:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="d343d-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="d343d-104">При запуске мастера сертификатов следует убедиться, что вход выполнен с использованием учетной записи, являющейся членом группы, которой назначены соответствующие разрешения для используемого шаблона сертификата.</span><span class="sxs-lookup"><span data-stu-id="d343d-104">When you run the Certificate Wizard, ensure that you are logged in using an account that is a member of a group that has been assigned the appropriate permissions for the type of certificate template you will use.</span></span> <span data-ttu-id="d343d-105">По умолчанию запрос сертификата Lync Server 2013 будет использовать шаблон сертификата веб-сервера.</span><span class="sxs-lookup"><span data-stu-id="d343d-105">By default, a Lync Server 2013 certificate request will use the Web Server certificate template.</span></span> <span data-ttu-id="d343d-106">Если вы используете учетную запись, которая является членом группы RTCUniversalServerAdmins, для запроса сертификата с использованием этого шаблона, убедитесь, что группе были назначены разрешения на регистрацию, которые необходимы для применения этого шаблона..</span><span class="sxs-lookup"><span data-stu-id="d343d-106">If you use an account that is a member of the RTCUniversalServerAdmins group to request a certificate using this template, verify that the group has been assigned the Enroll permissions required to use that template.</span></span>



</div>

<span data-ttu-id="d343d-107">Каждому директору требуется сертификат по умолчанию, внутренний веб-сертификат и внешний веб-сертификат.</span><span class="sxs-lookup"><span data-stu-id="d343d-107">Each Director requires a default certificate, a web internal certificate, and a web external certificate.</span></span> <span data-ttu-id="d343d-108">Сведения о требованиях к сертификатам для директоров приведены в статье [требования к сертификатам для внутренних серверов в Lync Server 2013](lync-server-2013-certificate-requirements-for-internal-servers.md) в документации по планированию.</span><span class="sxs-lookup"><span data-stu-id="d343d-108">For details about the certificate requirements for Directors, see [Certificate requirements for internal servers in Lync Server 2013](lync-server-2013-certificate-requirements-for-internal-servers.md) in the Planning documentation.</span></span>

<span data-ttu-id="d343d-p103">Используйте следующую процедуру для настройки сертификатов директоров. Повторите эту процедуру для каждого директора. Эта пошаговая процедура представляет собой процесс настройки сертификата, предоставленного центром сертификации Internal Enterprise Root, развернутым вашей организацией, с автономной обработкой запроса. Чтобы получить дополнительные сведения о получении сертификатов, предоставляемых внешним центром сертификации, обратитесь в отдел поддержки.</span><span class="sxs-lookup"><span data-stu-id="d343d-p103">Use the following procedure to configure Director certificates. Repeat the procedure for each Director. The steps of this procedure describe how to configure a certificate from an Internal Enterprise Root certification authority (CA) deployed by your organization and with offline request processing. For details about obtaining certificates from an external CA, contact your support team.</span></span>

<div>

## <a name="to-configure-certificates-for-the-director-or-director-pool"></a><span data-ttu-id="d343d-113">Настройка сертификатов для директора или пула директоров</span><span class="sxs-lookup"><span data-stu-id="d343d-113">To configure certificates for the Director or Director pool</span></span>

1.  <span data-ttu-id="d343d-114">В мастере развертывания Lync Server рядом с **шагом 3: запрос, установка или назначение сертификатов**нажмите кнопку **выполнить**.</span><span class="sxs-lookup"><span data-stu-id="d343d-114">In the Lync Server Deployment Wizard, next to **Step 3: Request, Install or Assign Certificates**, click **Run**.</span></span>

2.  <span data-ttu-id="d343d-115">На странице **Мастер сертификатов** щелкните **Запрос**.</span><span class="sxs-lookup"><span data-stu-id="d343d-115">On the **Certificate Wizard** page, click **Request**.</span></span>

3.  <span data-ttu-id="d343d-116">На странице **Запрос сертификата** щелкните **Далее**.</span><span class="sxs-lookup"><span data-stu-id="d343d-116">On the **Certificate Request** page, click **Next**.</span></span>

4.  <span data-ttu-id="d343d-117">На странице **Отложенные или немедленные запросы** сохраните значение по умолчанию **Немедленно отправить запрос в локальную службу сертификации**, а затем щелкните **Далее**.</span><span class="sxs-lookup"><span data-stu-id="d343d-117">On the **Delayed or Immediate Requests** page, accept the default **Send the request immediately to an online certification authority** option, and then click **Next**.</span></span>

5.  <span data-ttu-id="d343d-118">На странице **Выбор службы сертификации** щелкните внутренний центр сертификации Windows, который необходимо использовать, а затем щелкните **Далее**.</span><span class="sxs-lookup"><span data-stu-id="d343d-118">On the **Choose a Certification Authority (CA)** page, click the internal Windows certification authority that you want to use, and then click **Next**.</span></span>

6.  <span data-ttu-id="d343d-119">На странице **Учетная запись центра сертификации** укажите альтернативные учетные данные для использования в том случае, если у учетной записи, используемой для входа в систему, отсутствуют достаточные полномочия для запроса сертификата, а затем щелкните **Далее**.</span><span class="sxs-lookup"><span data-stu-id="d343d-119">On the **Certification Authority Account** page, specify alternate credentials to be used if the account you are logged on with does not have sufficient authority to request the certificate, and then click **Next**.</span></span>

7.  <span data-ttu-id="d343d-120">На странице **Укажите альтернативный шаблон сертификата** щелкните **Далее**.</span><span class="sxs-lookup"><span data-stu-id="d343d-120">On the **Specify Alternate Certificate Template** page, click **Next**.</span></span>

8.  <span data-ttu-id="d343d-121">На странице **Настройка имени и безопасности** можно указать **Понятное имя** и принять 2048-битовый ключ. Затем щелкните **Далее**.</span><span class="sxs-lookup"><span data-stu-id="d343d-121">On the **Name and Security Settings** page, you can specify a **Friendly Name**, accept the 2048-bit key length, and then click **Next**.</span></span>

9.  <span data-ttu-id="d343d-122">На странице **Сведения об организации** можно дополнительно указать сведения об организации. Затем щелкните **Далее**.</span><span class="sxs-lookup"><span data-stu-id="d343d-122">On the **Organization Information** page, optionally specify organization information, and then click **Next**.</span></span>

10. <span data-ttu-id="d343d-123">На странице **Сведения о местоположении** можно дополнительно указать географические сведения. Затем щелкните **Далее**.</span><span class="sxs-lookup"><span data-stu-id="d343d-123">On the **Geographical Information** page, optionally specify geographical information, and then click **Next**.</span></span>

11. <span data-ttu-id="d343d-124">На странице **Имя субъекта/альтернативные имена субъекта** щелкните **Далее**.</span><span class="sxs-lookup"><span data-stu-id="d343d-124">On the **Subject Name / Subject Alternative Names** page, click **Next**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="d343d-125">Список альтернативных имен субъектов должен содержать имя компьютера, на котором устанавливается директор (если используется один директор) или имя пула директоров, а также простые URL-адреса, настроенные для организации.</span><span class="sxs-lookup"><span data-stu-id="d343d-125">The subject alternative name list should contain the name of the computer on which you are installing the Director (if a single Director) or the Director pool name, and the simple URL names configured for the organization.</span></span>

    
    </div>

12. <span data-ttu-id="d343d-126">На странице **Настройка домена SIP для альтернативных имена субъект (SAN)** выберите **Настроенные домены SIP** для всех доменов, которые должен обрабатывать директор, а затем щелкните **Далее**.</span><span class="sxs-lookup"><span data-stu-id="d343d-126">On the **SIP Domain Setting on Subject Alternate Names (SANs)** page, select the **Configured SIP Domains** for all domains that you want the Director to handle, and then click **Next**.</span></span>

13. <span data-ttu-id="d343d-127">На странице **Настроить дополнительные альтернативные имена субъекта** добавьте любые дополнительные необходимые альтернативные имена субъекта, затем щелкните **Далее**.</span><span class="sxs-lookup"><span data-stu-id="d343d-127">On the **Configure Additional Subject Alternative Names** page, add any additional required subject alternative names, and then click **Next**.</span></span>

14. <span data-ttu-id="d343d-128">На странице **Сводка по запросам сертификатов** щелкните **Далее**.</span><span class="sxs-lookup"><span data-stu-id="d343d-128">On the **Certificate Request Summary** page, click **Next**.</span></span>

15. <span data-ttu-id="d343d-129">На странице **Выполнение команд** щелкните **Далее** после завершения выполнения команд.</span><span class="sxs-lookup"><span data-stu-id="d343d-129">On the **Executing Commands** page, click **Next** after the commands have finished running.</span></span>

16. <span data-ttu-id="d343d-130">На странице **Состояние запроса сертификата** щелкните **Готово**.</span><span class="sxs-lookup"><span data-stu-id="d343d-130">On the **Online Certificate Request Status** page, click **Finish**.</span></span>

17. <span data-ttu-id="d343d-131">На странице **Назначение сертификата** щелкните **Далее**.</span><span class="sxs-lookup"><span data-stu-id="d343d-131">On the **Certificate Assignment** page, click **Next**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="d343d-132">Если необходимо просмотреть сертификат, дважды щелкните его в списке.</span><span class="sxs-lookup"><span data-stu-id="d343d-132">if you want to view the certificate, double-click the certificate in the list.</span></span>

    
    </div>

18. <span data-ttu-id="d343d-133">На странице **Сводка по назначениям сертификатов** щелкните **Далее**.</span><span class="sxs-lookup"><span data-stu-id="d343d-133">On the **Certificate Assignment Summary** page, click **Next**.</span></span>

19. <span data-ttu-id="d343d-134">На странице **Выполнение команд** щелкните **Готово** после завершения выполнения команд.</span><span class="sxs-lookup"><span data-stu-id="d343d-134">On the **Executing Commands** page, click **Finish** after the commands have finished running.</span></span>

20. <span data-ttu-id="d343d-135">На странице **Мастер сертификатов** щелкните **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="d343d-135">On the **Certificate Wizard** page, click **Close**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

