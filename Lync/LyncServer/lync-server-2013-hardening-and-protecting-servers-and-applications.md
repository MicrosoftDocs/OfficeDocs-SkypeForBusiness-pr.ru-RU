---
title: 'Lync Server 2013: усиление защиты и защита серверов и приложений'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Hardening and protecting servers and applications for Lync Server 2013
ms:assetid: 9ca2b233-26f1-4d72-96e7-81a82c727806
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn518331(v=OCS.15)
ms:contentKeyID: 62625491
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3533bcf01338a056bab8c75d1409530fab7c901f
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48536886"
---
# <a name="hardening-and-protecting-servers-and-applications-for-lync-server-2013"></a><span data-ttu-id="17c5a-102">Усиление защиты и защита серверов и приложений для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="17c5a-102">Hardening and protecting servers and applications for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="17c5a-103">_**Последнее изменение темы:** 2013-12-05_</span><span class="sxs-lookup"><span data-stu-id="17c5a-103">_**Topic Last Modified:** 2013-12-05_</span></span>

<span data-ttu-id="17c5a-104">Необходимо защищать и защищать операционную систему и приложения в соответствии с рекомендациями по этому конкретному компоненту.</span><span class="sxs-lookup"><span data-stu-id="17c5a-104">You should harden and protect your operating system and applications according to best practices for that specific component.</span></span> <span data-ttu-id="17c5a-105">В этом разделе описывается, как защитить серверы приложений и использовать групповую политику для реализации блокирования безопасности.</span><span class="sxs-lookup"><span data-stu-id="17c5a-105">This section describes how to harden application servers and use Group Policy to implement security lockdowns.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="17c5a-106">Кроме того, можно защитить и защитить базы данных, используемые при развертывании Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="17c5a-106">You can also harden and protect the databases used for you Microsoft Lync Server 2013 deployment.</span></span> <span data-ttu-id="17c5a-107">Сведения о том, как защитить <A href="lync-server-2013-hardening-and-protecting-databases.md">и защитить базы данных Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="17c5a-107">For details, see <A href="lync-server-2013-hardening-and-protecting-databases.md">Hardening and protecting the databases of Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="securing-application-servers"></a><span data-ttu-id="17c5a-108">Защита серверов приложений</span><span class="sxs-lookup"><span data-stu-id="17c5a-108">Securing Application Servers</span></span>

<span data-ttu-id="17c5a-109">Для серверов приложений операционная система и приложение должны быть защищены.</span><span class="sxs-lookup"><span data-stu-id="17c5a-109">For applications servers, the operating system and the application should be hardened.</span></span> <span data-ttu-id="17c5a-110">Например, компьютер с Windows Server 2008, предназначенный для работы с Microsoft Internet Security and Acceleration (ISA) Server 2006, должен быть защищен от операционной системы и от перспективы приложения.</span><span class="sxs-lookup"><span data-stu-id="17c5a-110">For example, a Windows Server 2008 computer dedicated to running Microsoft Internet Security and Acceleration (ISA) Server 2006 should be hardened from the operating system and from the application perspective.</span></span> <span data-ttu-id="17c5a-111">Сведение к минимуму числа служб, выполняемых и предоставляемых сервером, должно быть основной задачей.</span><span class="sxs-lookup"><span data-stu-id="17c5a-111">Minimizing the number of services running and provided by the server should be a primary goal.</span></span>

</div>

<div>

## <a name="securing-virtual-servers"></a><span data-ttu-id="17c5a-112">Защита виртуальных серверов</span><span class="sxs-lookup"><span data-stu-id="17c5a-112">Securing Virtual Servers</span></span>

<span data-ttu-id="17c5a-113">Моментальные снимки виртуального сервера содержат копии дисков данных сервера и также содержат дампы данных в памяти, которые могут содержать конфиденциальные криптографические данные, которые могут привести к атакам.</span><span class="sxs-lookup"><span data-stu-id="17c5a-113">Virtual server snapshots contain copies of the server’s data disks and also contain dumps of in-memory data, both of which can contain sensitive cryptographic data that might lead to attacks.</span></span> <span data-ttu-id="17c5a-114">Для рабочих серверов, реализованных с помощью виртуализации, необходимо отключить все моментальные снимки сервера или управлять ими очень контролируемым образом.</span><span class="sxs-lookup"><span data-stu-id="17c5a-114">For production servers implemented using virtualization, you should disable all server snapshots or manage them in a very controlled manner.</span></span> <span data-ttu-id="17c5a-115">Подробнее об обеспечении безопасности виртуальных серверов Hyper # V вы найдете в руководстве по безопасности Hyper # V по адресу: [https://go.microsoft.com/fwlink/p/?LinkId=214176](https://go.microsoft.com/fwlink/p/?linkid=214176) .</span><span class="sxs-lookup"><span data-stu-id="17c5a-115">For details about securing Hyper-V virtual servers, see the Hyper-V Security Guide at: [https://go.microsoft.com/fwlink/p/?LinkId=214176](https://go.microsoft.com/fwlink/p/?linkid=214176).</span></span>

</div>

<div>

## <a name="group-policy"></a><span data-ttu-id="17c5a-116">Групповая политика</span><span class="sxs-lookup"><span data-stu-id="17c5a-116">Group Policy</span></span>

<span data-ttu-id="17c5a-117">В Windows Server 2008 и Windows Server 2008 R2 групповая политика обеспечивает управление конфигурацией настольных компьютеров на основе каталогов.</span><span class="sxs-lookup"><span data-stu-id="17c5a-117">In Windows Server 2008 and Windows Server 2008 R2, Group Policy provides directory-based desktop configuration management.</span></span> <span data-ttu-id="17c5a-118">Можно использовать групповую политику для реализации блокирования безопасности, определяя параметры компьютера и пользователя в объекте групповой политики (GPO) для следующих компонентов:</span><span class="sxs-lookup"><span data-stu-id="17c5a-118">You can use Group Policy to implement security lockdowns by defining Computer and User settings within a Group Policy object (GPO) for the following:</span></span>

  - <span data-ttu-id="17c5a-119">Политики на основе реестра</span><span class="sxs-lookup"><span data-stu-id="17c5a-119">Registry-based policies</span></span>

  - <span data-ttu-id="17c5a-120">Безопасность</span><span class="sxs-lookup"><span data-stu-id="17c5a-120">Security</span></span>

  - <span data-ttu-id="17c5a-121">Установка программного обеспечения</span><span class="sxs-lookup"><span data-stu-id="17c5a-121">Software installation</span></span>

  - <span data-ttu-id="17c5a-122">Сценарии</span><span class="sxs-lookup"><span data-stu-id="17c5a-122">Scripts</span></span>

  - <span data-ttu-id="17c5a-123">Перенаправление папок</span><span class="sxs-lookup"><span data-stu-id="17c5a-123">Folder redirection</span></span>

  - <span data-ttu-id="17c5a-124">Службы удаленной установки</span><span class="sxs-lookup"><span data-stu-id="17c5a-124">Remote installation services</span></span>

<span data-ttu-id="17c5a-125">Чтобы предоставить администратору пользовательский интерфейс для настройки этих параметров, административные шаблоны поставляются с выпусками операционной системы, выпусками пакетов обновления и некоторыми приложениями, включая Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="17c5a-125">To provide a user interface for the administrator to configure these settings, administrative templates are shipped with operating system releases, service pack releases, and some applications, including Lync Server 2013.</span></span>

<span data-ttu-id="17c5a-126">Файл Communicator. adm является административным шаблоном, который входит в состав Lync Server 2013, устанавливается в каталог% WINDIR% \\ inf \\ и предоставляет интерфейс для параметров групповой политики.</span><span class="sxs-lookup"><span data-stu-id="17c5a-126">The Communicator.adm file is an administrative template that ships with Lync Server 2013, is installed to the %windir%\\inf\\ directory, and provides an interface to the Group Policy settings.</span></span> <span data-ttu-id="17c5a-127">Каждый параметр в Communicator. adm соответствует параметру в реестре, влияющему на поведение приложения.</span><span class="sxs-lookup"><span data-stu-id="17c5a-127">Each setting in Communicator.adm corresponds to a setting in the registry that affects application behavior.</span></span>

<span data-ttu-id="17c5a-128">Доступ к параметрам можно получить в GPedit.dll, доступном в консоли "пользователи и компьютеры Active Directory" и в консоли управления групповыми политиками.</span><span class="sxs-lookup"><span data-stu-id="17c5a-128">The settings can be accessed from GPedit.dll, which is available from the Active Directory Users and Computers console and the Group Policy Management Console (GPMC).</span></span>

</div>

<div>

## <a name="group-policy-security-settings"></a><span data-ttu-id="17c5a-129">Параметры безопасности групповой политики</span><span class="sxs-lookup"><span data-stu-id="17c5a-129">Group Policy Security Settings</span></span>

<span data-ttu-id="17c5a-130">Групповая политика содержит параметры безопасности для объекта групповой политики в разделе Конфигурация компьютера/параметры Windows/параметры безопасности при доступе к GPedit.dll.</span><span class="sxs-lookup"><span data-stu-id="17c5a-130">Group Policy contains security settings for a GPO under Computer Configuration/Windows Settings/Security Settings when accessed from GPedit.dll.</span></span> <span data-ttu-id="17c5a-131">Шаблоны безопасности можно импортировать для настройки параметров безопасности для объекта групповой политики.</span><span class="sxs-lookup"><span data-stu-id="17c5a-131">You can import security templates to configure security settings for the GPO.</span></span> <span data-ttu-id="17c5a-132">Руководство по безопасности Windows Server 2008 [https://go.microsoft.com/fwlink/p/?LinkId=145186](https://go.microsoft.com/fwlink/p/?linkid=145186) и набор средств управления соответствием требованиям безопасности для Windows server 2008 R2 [https://go.microsoft.com/fwlink/p/?LinkId=211882](https://go.microsoft.com/fwlink/p/?linkid=211882) содержат несколько примеров шаблонов, которые можно изменить в соответствии с вашими потребностями.</span><span class="sxs-lookup"><span data-stu-id="17c5a-132">The Windows Server 2008 Security Guide at [https://go.microsoft.com/fwlink/p/?LinkId=145186](https://go.microsoft.com/fwlink/p/?linkid=145186) and the Windows Server 2008 R2 Security Compliance Management Toolkit at [https://go.microsoft.com/fwlink/p/?LinkId=211882](https://go.microsoft.com/fwlink/p/?linkid=211882) contain a number of sample templates that you can modify to meet your needs.</span></span>

</div>

<div>

## <a name="best-practices"></a><span data-ttu-id="17c5a-133">Рекомендации</span><span class="sxs-lookup"><span data-stu-id="17c5a-133">Best Practices</span></span>

  - <span data-ttu-id="17c5a-134">Заукрепление всех серверных операционных систем и приложений.</span><span class="sxs-lookup"><span data-stu-id="17c5a-134">Harden all server operating systems and applications.</span></span>

  - <span data-ttu-id="17c5a-135">Защита моментальных снимков сервера и улучшение безопасности всех виртуальных серверов.</span><span class="sxs-lookup"><span data-stu-id="17c5a-135">Protect server snapshots and enhance the security of all virtual servers.</span></span>

  - <span data-ttu-id="17c5a-136">Используйте групповую политику для реализации блокирования безопасности.</span><span class="sxs-lookup"><span data-stu-id="17c5a-136">Use Group Policy to implement security lockdowns.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

