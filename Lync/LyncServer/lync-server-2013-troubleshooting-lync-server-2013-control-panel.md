---
title: 'Lync Server 2013: Устранение неполадок с панелью управления Lync Server 2013'
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
ms.openlocfilehash: ff82a1e63a064d0053fc77614d6a9b5fa818c23e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41745019"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="troubleshooting-lync-server-2013-control-panel"></a><span data-ttu-id="876c1-102">Устранение неполадок с панелью управления Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="876c1-102">Troubleshooting Lync Server 2013 Control Panel</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="876c1-103">_**Тема последнего изменения:** 2016-07-28_</span><span class="sxs-lookup"><span data-stu-id="876c1-103">_**Topic Last Modified:** 2016-07-28_</span></span>

<span data-ttu-id="876c1-104">В этом разделе приведены сведения и процедуры, которые помогут вам устранить неполадки при доступе к панели управления Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="876c1-104">This topic provides information and procedures that can help you troubleshoot access to Lync Server 2013 Control Panel.</span></span>

<div>

## <a name="internet-browser-requirements"></a><span data-ttu-id="876c1-105">Требования к Интернет-браузеру</span><span class="sxs-lookup"><span data-stu-id="876c1-105">Internet Browser Requirements</span></span>

<span data-ttu-id="876c1-106">Для работы с панелью управления Lync Server необходимо установить подключаемый модуль Microsoft Silverlight версии 4.0.50524.0 или последней версии.</span><span class="sxs-lookup"><span data-stu-id="876c1-106">Lync Server Control Panel requires that Microsoft Silverlight browser plug-in version 4.0.50524.0 or latest version is installed.</span></span> <span data-ttu-id="876c1-107">Если приложение Silverlight не установлено или установлена более ранняя версия, следуйте инструкциям в сообщении, чтобы установить требуемую версию.</span><span class="sxs-lookup"><span data-stu-id="876c1-107">If Silverlight is not installed or if an earlier version is installed, follow the instructions in the message to install the required version.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="876c1-108">Другие требования к программному обеспечению для панели управления Lync Server относятся к операционной системе, в которой можно установить панель управления Lync Server и другие средства администрирования Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="876c1-108">Other software requirements for Lync Server Control Panel pertain to the operating system on which Lync Server Control Panel and all other Lync Server 2013 administrative tools can be installed.</span></span> <span data-ttu-id="876c1-109">Подробности можно найти в разделе <A href="lync-server-2013-server-and-tools-operating-system-support.md">Поддержка серверов и инструментальных средств операционной системы в Lync Server 2013</A> в документации по поддержке.</span><span class="sxs-lookup"><span data-stu-id="876c1-109">For details, see <A href="lync-server-2013-server-and-tools-operating-system-support.md">Server and tools operating system support in Lync Server 2013</A> in the Supportability documentation.</span></span>



</div>

<span data-ttu-id="876c1-110">Если ваш браузер сети заблокирует установку Silverlight из-за соображений безопасности, добавьте URL-адрес, который открывает панель управления Lync Server в списке надежных сайтов.</span><span class="sxs-lookup"><span data-stu-id="876c1-110">If your Internet browser blocks installation of Silverlight due to security considerations, add the Uniform Resource Locator (URL) that opens Lync Server Control Panel to the list of trusted sites.</span></span> <span data-ttu-id="876c1-111">В параметрах безопасности Internet Explorer убедитесь, что для параметра **Запуск элементов ActiveX и подключаемых модулей** задано значение **включено**.</span><span class="sxs-lookup"><span data-stu-id="876c1-111">In Internet Explorer security settings, ensure that **Run ActiveX controls and plug-ins** is set to **Enabled**.</span></span> <span data-ttu-id="876c1-112">Подробности можно найти в [http://go.microsoft.com/fwlink/p/?linkId=214060](http://go.microsoft.com/fwlink/p/?linkid=214060)разделе.</span><span class="sxs-lookup"><span data-stu-id="876c1-112">For details, see [http://go.microsoft.com/fwlink/p/?linkId=214060](http://go.microsoft.com/fwlink/p/?linkid=214060).</span></span> <span data-ttu-id="876c1-113">Кроме того, убедитесь, что браузер настроен на использование SSL 3,0.</span><span class="sxs-lookup"><span data-stu-id="876c1-113">Furthermore, ensure that the browser is configured to use SSL 3.0.</span></span>

<span data-ttu-id="876c1-114">Если браузер настроен на использование прокси-сервера, убедитесь, что он настроен таким образом, чтобы он обходил прокси-сервер для сайтов, автоматически обнаруживаемых как внутренние сайты.</span><span class="sxs-lookup"><span data-stu-id="876c1-114">If the Internet browser is configured to use a proxy server, verify that the browser is configured to bypass the proxy server for sites that are automatically detected as internal sites.</span></span> <span data-ttu-id="876c1-115">Вы также можете добавить адрес в список исключений браузера в параметрах конфигурации прокси-сервера.</span><span class="sxs-lookup"><span data-stu-id="876c1-115">Or, add the address to the browser's exception list in the proxy server configuration settings.</span></span>

</div>

<div>

## <a name="dns-record-and-certificate-requirements-for-the-administrative-access-url"></a><span data-ttu-id="876c1-116">Требования к записям DNS и сертификатам для URL-адреса административного доступа</span><span class="sxs-lookup"><span data-stu-id="876c1-116">DNS Record and Certificate Requirements for the Administrative Access URL</span></span>

<span data-ttu-id="876c1-117">Если вы настроили простой URL-адрес для доступа к панели управления Lync Server, убедитесь, что вы также настроили статическую запись ресурса узла (A) доменных имен (DNS) и сертификат, необходимый для использования URL-адреса для административного доступа.</span><span class="sxs-lookup"><span data-stu-id="876c1-117">If you configured a simple URL to access Lync Server Control Panel, ensure that you also configured the static Domain Name System (DNS) host (A) resource record and certificate necessary to use that administrative access URL.</span></span> <span data-ttu-id="876c1-118">Если вы в любой момент измените базовый URL-адрес, убедитесь, что изменения отражаются в соответствующей записи DNS и сертификате, и что вы запускаете *Enable-кскомпутер* для каждого директора и сервера переднего плана для регистрации изменения.</span><span class="sxs-lookup"><span data-stu-id="876c1-118">If you change the base URL at any time, ensure that the change is reflected in the appropriate DNS record and certificate and that you run the *Enable-CsComputer* on each Director and Front End Server to register the change.</span></span> <span data-ttu-id="876c1-119">Подробные сведения можно найти в следующих статьях в документации по планированию.</span><span class="sxs-lookup"><span data-stu-id="876c1-119">For details, see the following topics in the Planning documentation:</span></span>

  - [<span data-ttu-id="876c1-120">Планирование простых URL-адресов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="876c1-120">Planning for simple URLs in Lync Server 2013</span></span>](lync-server-2013-planning-for-simple-urls.md)

  - [<span data-ttu-id="876c1-121">Требования DNS для простых URL-адресов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="876c1-121">DNS requirements for simple URLs in Lync Server 2013</span></span>](lync-server-2013-dns-requirements-for-simple-urls.md)

  - [<span data-ttu-id="876c1-122">Требования к сертификатам для внутренних серверов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="876c1-122">Certificate requirements for internal servers in Lync Server 2013</span></span>](lync-server-2013-certificate-requirements-for-internal-servers.md)

<span data-ttu-id="876c1-123">Пошаговые инструкции по настройке URL-адреса для административного доступа можно найти [в статье изменение и настройка простых адресов URL в Lync Server 2013](lync-server-2013-edit-or-configure-simple-urls.md) в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="876c1-123">For step-by-step procedures to configure the administrative access URL, see [Edit or configure simple URLs in Lync Server 2013](lync-server-2013-edit-or-configure-simple-urls.md) in the Deployment documentation.</span></span>

</div>

<div>

## <a name="internet-information-services-iis-requirements"></a><span data-ttu-id="876c1-124">Требования к службам IIS</span><span class="sxs-lookup"><span data-stu-id="876c1-124">Internet Information Services (IIS) Requirements</span></span>

<span data-ttu-id="876c1-125">Панель управления Lync Server — это один из компонентов Lync Server 2013, для работы с которым требуются информационные службы Интернета (IIS).</span><span class="sxs-lookup"><span data-stu-id="876c1-125">Lync Server Control Panel is one of the components of Lync Server 2013 that requires Internet Information Services (IIS).</span></span> <span data-ttu-id="876c1-126">В частности, убедитесь, что включена функция перенаправления HTTP и проверки подлинности Windows, и что служба веб-публикации (W3SVC) запущена.</span><span class="sxs-lookup"><span data-stu-id="876c1-126">In particular, ensure that HTTP redirection and Windows authentication features are enabled, and that the World Wide Web Publishing Service (W3SVC) is running.</span></span>

<div>

## <a name="world-wide-publishing-service-windows-service-dependency"></a><span data-ttu-id="876c1-127">Зависимость службы публикации в глобальной среде (Windows)</span><span class="sxs-lookup"><span data-stu-id="876c1-127">World Wide Publishing Service (Windows Service) Dependency</span></span>

<span data-ttu-id="876c1-128">Когда служба веб-публикации остановлена, вы не можете получить доступ к панели управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="876c1-128">When the World Wide Web Publishing Service is stopped, you cannot access Lync Server Control Panel.</span></span> <span data-ttu-id="876c1-129">Вы можете перезапустить службу с помощью консоли управления службами Windows (MMC).</span><span class="sxs-lookup"><span data-stu-id="876c1-129">You can restart the service by using the Windows Services Microsoft Management Console (MMC).</span></span>

<span data-ttu-id="876c1-130">**Запуск службы публикации в Интернете**</span><span class="sxs-lookup"><span data-stu-id="876c1-130">**To start the World Wide Web Publishing Service**</span></span>

1.  <span data-ttu-id="876c1-131">Войдите в систему с компьютера, на котором установлена служба веб-публикации, в составе служб Internet Information Services (IIS).</span><span class="sxs-lookup"><span data-stu-id="876c1-131">Log on to the computer where the World Wide Web Publishing Service is installed as part of Internet Information Services (IIS).</span></span>

2.  <span data-ttu-id="876c1-132">Нажмите кнопку **Пуск**, выберите пункт **Администрирование**, а затем — пункт **службы**.</span><span class="sxs-lookup"><span data-stu-id="876c1-132">Click **Start**, click **Administrative Tools**, and then click **Services**.</span></span>

3.  <span data-ttu-id="876c1-133">Щелкните правой кнопкой мыши **службу публикации**в Интернете и выберите команду **Пуск**.</span><span class="sxs-lookup"><span data-stu-id="876c1-133">Right-click **World Wide Web Publishing Service**, and then click **Start**.</span></span>

</div>

<div>

## <a name="application-pool-mode"></a><span data-ttu-id="876c1-134">Режим пула приложений</span><span class="sxs-lookup"><span data-stu-id="876c1-134">Application Pool Mode</span></span>

<span data-ttu-id="876c1-135">Настройте IIS таким образом, чтобы в качестве удостоверения модели процессов в пуле приложений Ксманажементапппул использовалась учетная запись Network Service.</span><span class="sxs-lookup"><span data-stu-id="876c1-135">Configure IIS so that the CsManagementAppPool application pool uses the Network Service account as its process model identity.</span></span>

</div>

</div>

<div>

## <a name="user-rights-and-permissions"></a><span data-ttu-id="876c1-136">Права и разрешения пользователей</span><span class="sxs-lookup"><span data-stu-id="876c1-136">User Rights and Permissions</span></span>

<span data-ttu-id="876c1-137">Вы должны войти на панель управления Lync Server с помощью учетной записи домена, которая входит в группу Ксадминистратор, или с помощью учетной записи, которой делегированы права и разрешения пользователей.</span><span class="sxs-lookup"><span data-stu-id="876c1-137">You must sign in to Lync Server Control Panel either by using a domain account that is a member of the CsAdministrator group or by using an account to which you have delegated user rights and permissions.</span></span> <span data-ttu-id="876c1-138">Вы не можете войти на панель управления Lync Server с помощью учетной записи локального компьютера.</span><span class="sxs-lookup"><span data-stu-id="876c1-138">You cannot sign in to Lync Server Control Panel by using a local machine account.</span></span> <span data-ttu-id="876c1-139">Сведения о делегировании административных задач с помощью управления доступом на основе ролей (RBAC) можно найти [в разделе Планирование управления доступом на основе ролей в Lync Server 2013](lync-server-2013-planning-for-role-based-access-control.md) в документации по планированию.</span><span class="sxs-lookup"><span data-stu-id="876c1-139">For details about delegating administrative tasks through role-based access control (RBAC), see [Planning for role-based access control in Lync Server 2013](lync-server-2013-planning-for-role-based-access-control.md) in the Planning documentation.</span></span>

<span data-ttu-id="876c1-140">Если вы используете простой URL-адрес для доступа к панели управления Lync Server, убедитесь, что веб-серверы добавлены в группы Рткуниверсалсерверадминс и Рткуниверсалусерадминс.</span><span class="sxs-lookup"><span data-stu-id="876c1-140">If you use a simple URL to access Lync Server Control Panel, ensure that web servers are added to the RTCUniversalServerAdmins and RTCUniversalUserAdmins groups.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="876c1-141">См. также</span><span class="sxs-lookup"><span data-stu-id="876c1-141">See Also</span></span>


[<span data-ttu-id="876c1-142">Средства администрирования Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="876c1-142">Lync Server 2013 administrative tools</span></span>](lync-server-2013-lync-server-administrative-tools.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

