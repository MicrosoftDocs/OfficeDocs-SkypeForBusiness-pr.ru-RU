---
title: 'Lync Server 2013: Устранение неполадок в панели управления Lync Server 2013'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Troubleshooting Lync Server 2013 Control Panel
ms:assetid: 54e7ab57-34ce-4a07-bcc9-643379eb4eb7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg195689(v=OCS.15)
ms:contentKeyID: 48184145
ms.date: 07/28/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b7da23bc56d18b1b5e6235551f7b99cc15e658fc
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48535936"
---
# <a name="troubleshooting-lync-server-2013-control-panel"></a><span data-ttu-id="4e783-102">Устранение неполадок с панелью управления в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4e783-102">Troubleshooting Lync Server 2013 Control Panel</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4e783-103">_**Последнее изменение темы:** 2016-07-28_</span><span class="sxs-lookup"><span data-stu-id="4e783-103">_**Topic Last Modified:** 2016-07-28_</span></span>

<span data-ttu-id="4e783-104">В этом разделе представлены сведения и процедуры, которые помогут устранить неполадки при доступе к панели управления Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4e783-104">This topic provides information and procedures that can help you troubleshoot access to Lync Server 2013 Control Panel.</span></span>

<div>

## <a name="internet-browser-requirements"></a><span data-ttu-id="4e783-105">Требования к Интернет-браузеру</span><span class="sxs-lookup"><span data-stu-id="4e783-105">Internet Browser Requirements</span></span>

<span data-ttu-id="4e783-106">Для панели управления Lync Server необходимо установить надстройку браузера Microsoft Silverlight версии 4.0.50524.0 или последней версии.</span><span class="sxs-lookup"><span data-stu-id="4e783-106">Lync Server Control Panel requires that Microsoft Silverlight browser plug-in version 4.0.50524.0 or latest version is installed.</span></span> <span data-ttu-id="4e783-107">Если Silverlight не установлен или если установлена более ранняя версия, следуйте инструкциям в сообщении, чтобы установить требуемую версию.</span><span class="sxs-lookup"><span data-stu-id="4e783-107">If Silverlight is not installed or if an earlier version is installed, follow the instructions in the message to install the required version.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="4e783-108">Другие требования к программному обеспечению для панели управления Lync Server относятся к операционной системе, в которой можно установить панель управления Lync Server и все остальные средства администрирования Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4e783-108">Other software requirements for Lync Server Control Panel pertain to the operating system on which Lync Server Control Panel and all other Lync Server 2013 administrative tools can be installed.</span></span> <span data-ttu-id="4e783-109">Для получения дополнительных сведений обратитесь к разделу <A href="lync-server-2013-server-and-tools-operating-system-support.md">Поддержка серверов и средств операционной системы в Lync Server 2013</A> в документации по поддержке.</span><span class="sxs-lookup"><span data-stu-id="4e783-109">For details, see <A href="lync-server-2013-server-and-tools-operating-system-support.md">Server and tools operating system support in Lync Server 2013</A> in the Supportability documentation.</span></span>



</div>

<span data-ttu-id="4e783-110">Если ваш Интернет-браузер блокирует установку Silverlight из-за соображений безопасности, добавьте URL-адрес, который открывает панель управления Lync Server, в список надежных сайтов.</span><span class="sxs-lookup"><span data-stu-id="4e783-110">If your Internet browser blocks installation of Silverlight due to security considerations, add the Uniform Resource Locator (URL) that opens Lync Server Control Panel to the list of trusted sites.</span></span> <span data-ttu-id="4e783-111">В параметрах безопасности Internet Explorer убедитесь, что параметр **Запускать элементы ActiveX и подключаемые модули\*\*\*\*включен**.</span><span class="sxs-lookup"><span data-stu-id="4e783-111">In Internet Explorer security settings, ensure that **Run ActiveX controls and plug-ins** is set to **Enabled**.</span></span> <span data-ttu-id="4e783-112">Дополнительные сведения см [https://go.microsoft.com/fwlink/p/?linkId=214060](https://go.microsoft.com/fwlink/p/?linkid=214060) .</span><span class="sxs-lookup"><span data-stu-id="4e783-112">For details, see [https://go.microsoft.com/fwlink/p/?linkId=214060](https://go.microsoft.com/fwlink/p/?linkid=214060).</span></span> <span data-ttu-id="4e783-113">Кроме того, убедитесь, что браузер настроен для использования SSL 3.0.</span><span class="sxs-lookup"><span data-stu-id="4e783-113">Furthermore, ensure that the browser is configured to use SSL 3.0.</span></span>

<span data-ttu-id="4e783-p104">Если Интернет-браузер настроен для использования прокси-сервера, то убедитесь, что задан обход прокси-сервера для сайтов, которые автоматически определяются как внутренние сайты. Можно также добавить этот адрес в список исключений браузера в параметрах конфигурации прокси-сервера.</span><span class="sxs-lookup"><span data-stu-id="4e783-p104">If the Internet browser is configured to use a proxy server, verify that the browser is configured to bypass the proxy server for sites that are automatically detected as internal sites. Or, add the address to the browser's exception list in the proxy server configuration settings.</span></span>

</div>

<div>

## <a name="dns-record-and-certificate-requirements-for-the-administrative-access-url"></a><span data-ttu-id="4e783-116">Требования к записи DNS и к сертификату для URL-адреса административного доступа</span><span class="sxs-lookup"><span data-stu-id="4e783-116">DNS Record and Certificate Requirements for the Administrative Access URL</span></span>

<span data-ttu-id="4e783-117">Если вы настроили простой URL-адрес для доступа к панели управления Lync Server, убедитесь, что вы также настроили статическую запись ресурса узла (DNS) узла (A) и сертификат, необходимый для использования этого URL-адреса административного доступа.</span><span class="sxs-lookup"><span data-stu-id="4e783-117">If you configured a simple URL to access Lync Server Control Panel, ensure that you also configured the static Domain Name System (DNS) host (A) resource record and certificate necessary to use that administrative access URL.</span></span> <span data-ttu-id="4e783-118">Если изменить базовый URL-адрес в любой момент времени, убедитесь, что изменение отражается в соответствующей записи DNS и в сертификате, а также при запуске командлета *Enable-CsComputer* на каждом директоре и сервере переднего плана, чтобы зарегистрировать изменение.</span><span class="sxs-lookup"><span data-stu-id="4e783-118">If you change the base URL at any time, ensure that the change is reflected in the appropriate DNS record and certificate and that you run the *Enable-CsComputer* on each Director and Front End Server to register the change.</span></span> <span data-ttu-id="4e783-119">Подробные сведения см. в следующих разделах документации по планированию.</span><span class="sxs-lookup"><span data-stu-id="4e783-119">For details, see the following topics in the Planning documentation:</span></span>

  - [<span data-ttu-id="4e783-120">Планирование простых URL-адресов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4e783-120">Planning for simple URLs in Lync Server 2013</span></span>](lync-server-2013-planning-for-simple-urls.md)

  - [<span data-ttu-id="4e783-121">Требования DNS для простых URL-адресов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4e783-121">DNS requirements for simple URLs in Lync Server 2013</span></span>](lync-server-2013-dns-requirements-for-simple-urls.md)

  - [<span data-ttu-id="4e783-122">Требования к сертификатам для внутренних серверов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4e783-122">Certificate requirements for internal servers in Lync Server 2013</span></span>](lync-server-2013-certificate-requirements-for-internal-servers.md)

<span data-ttu-id="4e783-123">Пошаговые процедуры настройки URL-адреса административного доступа приведены в статье [изменение или Настройка простых URL-адресов в Lync Server 2013](lync-server-2013-edit-or-configure-simple-urls.md) в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="4e783-123">For step-by-step procedures to configure the administrative access URL, see [Edit or configure simple URLs in Lync Server 2013](lync-server-2013-edit-or-configure-simple-urls.md) in the Deployment documentation.</span></span>

</div>

<div>

## <a name="internet-information-services-iis-requirements"></a><span data-ttu-id="4e783-124">Требования служб IIS</span><span class="sxs-lookup"><span data-stu-id="4e783-124">Internet Information Services (IIS) Requirements</span></span>

<span data-ttu-id="4e783-125">Панель управления Lync Server — это один из компонентов Lync Server 2013, требующих служб IIS.</span><span class="sxs-lookup"><span data-stu-id="4e783-125">Lync Server Control Panel is one of the components of Lync Server 2013 that requires Internet Information Services (IIS).</span></span> <span data-ttu-id="4e783-126">В частности, следует убедиться, что включены функции перенаправления HTTP и проверки подлинности Windows, и что служба веб-публикаций (W3SVC) выполняется.</span><span class="sxs-lookup"><span data-stu-id="4e783-126">In particular, ensure that HTTP redirection and Windows authentication features are enabled, and that the World Wide Web Publishing Service (W3SVC) is running.</span></span>

<div>

## <a name="world-wide-publishing-service-windows-service-dependency"></a><span data-ttu-id="4e783-127">Зависимость от службы веб-публикаций (службы Windows)</span><span class="sxs-lookup"><span data-stu-id="4e783-127">World Wide Publishing Service (Windows Service) Dependency</span></span>

<span data-ttu-id="4e783-128">После остановки службы публикации в Интернете невозможно получить доступ к панели управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="4e783-128">When the World Wide Web Publishing Service is stopped, you cannot access Lync Server Control Panel.</span></span> <span data-ttu-id="4e783-129">Необходимо перезапустить эту службу с помощью консоли управления (MMC) служб Windows.</span><span class="sxs-lookup"><span data-stu-id="4e783-129">You can restart the service by using the Windows Services Microsoft Management Console (MMC).</span></span>

<span data-ttu-id="4e783-130">**Запуск службы веб-публикаций**</span><span class="sxs-lookup"><span data-stu-id="4e783-130">**To start the World Wide Web Publishing Service**</span></span>

1.  <span data-ttu-id="4e783-131">Войдите на компьютер, на котором установлена служба веб-публикации в составе служб IIS.</span><span class="sxs-lookup"><span data-stu-id="4e783-131">Log on to the computer where the World Wide Web Publishing Service is installed as part of Internet Information Services (IIS).</span></span>

2.  <span data-ttu-id="4e783-132">Нажмите кнопку **Пуск**, а затем последовательно выберите пункты **Администрирование** и **Службы**.</span><span class="sxs-lookup"><span data-stu-id="4e783-132">Click **Start**, click **Administrative Tools**, and then click **Services**.</span></span>

3.  <span data-ttu-id="4e783-133">Щелкните правой кнопкой мыши **службу веб-публикаций** и выберите команду **Пуск**.</span><span class="sxs-lookup"><span data-stu-id="4e783-133">Right-click **World Wide Web Publishing Service**, and then click **Start**.</span></span>

</div>

<div>

## <a name="application-pool-mode"></a><span data-ttu-id="4e783-134">Режим пула приложений</span><span class="sxs-lookup"><span data-stu-id="4e783-134">Application Pool Mode</span></span>

<span data-ttu-id="4e783-135">Настройте службы IIS таким образом, чтобы пул приложений CsManagementAppPool использовал учетную запись сетевой службы в качестве удостоверения своей модели процесса.</span><span class="sxs-lookup"><span data-stu-id="4e783-135">Configure IIS so that the CsManagementAppPool application pool uses the Network Service account as its process model identity.</span></span>

</div>

</div>

<div>

## <a name="user-rights-and-permissions"></a><span data-ttu-id="4e783-136">Пользовательские права и разрешения</span><span class="sxs-lookup"><span data-stu-id="4e783-136">User Rights and Permissions</span></span>

<span data-ttu-id="4e783-137">Необходимо войти на панель управления Lync Server с помощью учетной записи домена, которая является членом группы CsAdministrator, или с помощью учетной записи, которой делегированы права и разрешения пользователей.</span><span class="sxs-lookup"><span data-stu-id="4e783-137">You must sign in to Lync Server Control Panel either by using a domain account that is a member of the CsAdministrator group or by using an account to which you have delegated user rights and permissions.</span></span> <span data-ttu-id="4e783-138">Вы не можете войти на панель управления Lync Server, используя учетную запись локального компьютера.</span><span class="sxs-lookup"><span data-stu-id="4e783-138">You cannot sign in to Lync Server Control Panel by using a local machine account.</span></span> <span data-ttu-id="4e783-139">Дополнительные сведения о делегировании административных задач с помощью управления доступом на основе ролей (RBAC) можно найти в статье [Планирование управления доступом на основе ролей в Lync Server 2013](lync-server-2013-planning-for-role-based-access-control.md) в документации по планированию.</span><span class="sxs-lookup"><span data-stu-id="4e783-139">For details about delegating administrative tasks through role-based access control (RBAC), see [Planning for role-based access control in Lync Server 2013](lync-server-2013-planning-for-role-based-access-control.md) in the Planning documentation.</span></span>

<span data-ttu-id="4e783-140">Если вы используете простой URL-адрес для доступа к панели управления Lync Server, убедитесь, что веб-серверы добавлены в группы RTCUniversalServerAdmins и RTCUniversalUserAdmins.</span><span class="sxs-lookup"><span data-stu-id="4e783-140">If you use a simple URL to access Lync Server Control Panel, ensure that web servers are added to the RTCUniversalServerAdmins and RTCUniversalUserAdmins groups.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="4e783-141">См. также</span><span class="sxs-lookup"><span data-stu-id="4e783-141">See Also</span></span>


[<span data-ttu-id="4e783-142">Lync Server 2013 административные средства</span><span class="sxs-lookup"><span data-stu-id="4e783-142">Lync Server 2013 administrative tools</span></span>](lync-server-2013-lync-server-administrative-tools.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

