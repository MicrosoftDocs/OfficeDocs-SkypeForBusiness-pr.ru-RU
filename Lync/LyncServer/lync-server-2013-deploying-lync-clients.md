---
title: 'Lync Server 2013: развертывание клиентов Lync'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying Lync clients
ms:assetid: 3d10abf2-d484-4fa0-8f10-4a5f9dfba4f5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204827(v=OCS.15)
ms:contentKeyID: 48183925
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3d7f4497fb6842befba3f5facf5de023b94b4a76
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41733607"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-lync-clients-in-lync-server-2013"></a><span data-ttu-id="c48cf-102">Развертывание клиентов Lync в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c48cf-102">Deploying Lync clients in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c48cf-103">_**Тема последнего изменения:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="c48cf-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="c48cf-104">В Lync 2013 представлен другой подход к развертыванию клиента.</span><span class="sxs-lookup"><span data-stu-id="c48cf-104">Lync 2013 introduces a different approach to client deployment.</span></span> <span data-ttu-id="c48cf-105">В отъезде из предыдущих выпусков Lync 2013 больше не имеет собственного установщика.</span><span class="sxs-lookup"><span data-stu-id="c48cf-105">In a departure from previous releases, Lync 2013 no longer has its own installer.</span></span> <span data-ttu-id="c48cf-106">Вместо этого Lync входит в состав программы установки Office 2013.</span><span class="sxs-lookup"><span data-stu-id="c48cf-106">Instead, Lync is included with the Office 2013 setup program.</span></span> <span data-ttu-id="c48cf-107">Чтобы развернуть Lync 2013 для пользователей, вы можете использовать способы установки Office 2013 и средства настройки.</span><span class="sxs-lookup"><span data-stu-id="c48cf-107">To deploy Lync 2013 to your users, you can use Office 2013 installation methods and customization tools.</span></span>

  - <span data-ttu-id="c48cf-108">**Установщик windows 2013 Office** — это установочный пакет установщика Windows, состоящий из нескольких MSI-файлов.</span><span class="sxs-lookup"><span data-stu-id="c48cf-108">**Office 2013 Windows Installer** is a Windows Installer-based installation package that consists of multiple MSI files.</span></span> <span data-ttu-id="c48cf-109">Не зависящий от языка основной пакет MSI объединен с одним или несколькими языковыми пакетами, что в совокупности и представляет полный продукт.</span><span class="sxs-lookup"><span data-stu-id="c48cf-109">A language-neutral core MSI package is combined with one or more language-specific packages to make a complete product.</span></span> <span data-ttu-id="c48cf-110">При настройке отдельные пакеты собираются вместе и выполняются задачи настройки и обслуживания во время и после установки Office на пользовательские компьютеры.</span><span class="sxs-lookup"><span data-stu-id="c48cf-110">Setup assembles the individual packages and performs customization and maintenance tasks during and after installation of Office on users' computers.</span></span> <span data-ttu-id="c48cf-111">В этой статье описано, как использовать и настраивать установщик Windows 2013 для развертывания Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="c48cf-111">The topics in this section describe how to use and customize the Office 2013 Windows Installer to deploy Lync 2013.</span></span>

  - <span data-ttu-id="c48cf-112">**Office 2013 нажми и работай** — это программа установки, с помощью которой можно перепотокировать файлы установки Office на портале Microsoft Office 365.</span><span class="sxs-lookup"><span data-stu-id="c48cf-112">**Office 2013 Click-to-Run** is an installation program that streams Office setup files to the user from the Microsoft Office 365 portal.</span></span> <span data-ttu-id="c48cf-113">Администраторы могут настраивать установку с помощью средства развертывания Office для технологии "Нажми и работай".</span><span class="sxs-lookup"><span data-stu-id="c48cf-113">Administrators can customize installation by using the Office Deployment Tool for Click-to-Run.</span></span> <span data-ttu-id="c48cf-114">Поскольку в Office 2013 технология "нажми и работай" используется преимущественно в среде Microsoft Office 365, этот способ установки не подробно описан в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="c48cf-114">Because Office 2013 Click-to-Run is primarily used in the Microsoft Office 365 environment, this installation method is not described in detail in this section.</span></span> <span data-ttu-id="c48cf-115">Подробные сведения об использовании и настройке установки "нажми и работай" можно найти в документации по набору ресурсов Office 2013.</span><span class="sxs-lookup"><span data-stu-id="c48cf-115">Detailed information about using and customizing Click-to-Run installation is available in the Office 2013 Resource Kit documentation.</span></span> <span data-ttu-id="c48cf-116">Кроме того, администраторы могут загрузить файлы исходного кода и языковых файлов Office 2013 в локальное расположение, что бывает полезно, если вы хотите минимизировать требования к сети или запретить пользователям устанавливать программное обеспечение из Интернета из-за корпоративные требования к безопасности.</span><span class="sxs-lookup"><span data-stu-id="c48cf-116">Administrators can also download the Office 2013 Click-to-Run program and language source files to an on-premises location, which is useful when you want to minimize the demand on the network or prevent users from installing software from the Internet because of corporate security requirements.</span></span>

<span data-ttu-id="c48cf-117">В этом разделе содержатся сведения о развертывании клиентов с помощью установщика Office 2013 на базе MSI.</span><span class="sxs-lookup"><span data-stu-id="c48cf-117">The topics in this section focus on how to deploy clients by using the Office 2013 MSI-based installer.</span></span> <span data-ttu-id="c48cf-118">Основной ссылкой является документация по набору ресурсов Office 2013, в которой подробно описана процедура подготовки инфраструктуры, Настройка настройки и развертывание Office 2013.</span><span class="sxs-lookup"><span data-stu-id="c48cf-118">Your primary reference should be the Office 2013 Resource Kit documentation, which describes in detail how to prepare your infrastructure, customize setup, and deploy Office 2013.</span></span> <span data-ttu-id="c48cf-119">Тем не менее, вы должны использовать документацию Office в сочетании с разделами в этом разделе, которые указывают на вопросы по развертыванию, специфичные для Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="c48cf-119">However, you should use the Office documentation in conjunction with topics in this section, which point out deployment considerations that are specific to Lync 2013.</span></span>

<div>


> [!NOTE]  
> <UL>
> <LI>
> <P><span data-ttu-id="c48cf-120">Надстройка "собрание по сети" для Lync 2013, которая поддерживает управление собраниями в клиенте обмена сообщениями и совместной работы в Outlook, устанавливается автоматически с помощью Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="c48cf-120">The Online Meeting Add-in for Lync 2013, which supports meeting management from within the Outlook messaging and collaboration client, installs automatically with Lync 2013.</span></span></P>
> <LI>
> <P><span data-ttu-id="c48cf-121">Программа установки Office 2013 не удаляет предыдущие версии Lync и Office Communicator.</span><span class="sxs-lookup"><span data-stu-id="c48cf-121">The Office 2013 setup program does not uninstall previous versions of Lync or Office Communicator.</span></span> <span data-ttu-id="c48cf-122">Клиент Lync 2013 устанавливается параллельно с другими клиентами Lync или Office Communicator</span><span class="sxs-lookup"><span data-stu-id="c48cf-122">The Lync 2013 client installs side-by-side with other Lync or Office Communicator clients</span></span></P></LI></UL>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="c48cf-123">Содержание</span><span class="sxs-lookup"><span data-stu-id="c48cf-123">In This Section</span></span>

  - [<span data-ttu-id="c48cf-124">Настройка установки клиента в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c48cf-124">Customizing client installation in Lync Server 2013</span></span>](lync-server-2013-customizing-client-installation.md)

  - [<span data-ttu-id="c48cf-125">Настройка поведения Lync и пользовательского интерфейса в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c48cf-125">Customizing Lync behavior and the user interface in Lync Server 2013</span></span>](lync-server-2013-customizing-lync-behavior-and-the-user-interface.md)

  - [<span data-ttu-id="c48cf-126">Настройка надстройки "собрание по сети" в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c48cf-126">Customizing the Online Meeting Add-in in Lync Server 2013</span></span>](lync-server-2013-customizing-the-online-meeting-add-in.md)

  - [<span data-ttu-id="c48cf-127">Конфигурация страницы присоединения к собранию в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c48cf-127">Configuring the meeting join page in Lync Server 2013</span></span>](lync-server-2013-configuring-the-meeting-join-page.md)

  - [<span data-ttu-id="c48cf-128">Настройка поддерживаемых клиентских версий в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c48cf-128">Configuring supported client versions in Lync Server 2013</span></span>](lync-server-2013-configuring-supported-client-versions.md)

  - [<span data-ttu-id="c48cf-129">Настройка режима конфиденциальности для расширенного присутствия в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c48cf-129">Configuring enhanced presence privacy mode in Lync Server 2013</span></span>](lync-server-2013-configuring-enhanced-presence-privacy-mode.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

