---
title: 'Lync Server 2013: подготовка схемы Active Directory'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Preparing the Active Directory schema
ms:assetid: 067726ae-fd3f-4133-a32f-26d2603ac674
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398119(v=OCS.15)
ms:contentKeyID: 48183300
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: efabd082fce4dba5cf210e2c0f9c390324474cd2
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42201785"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="preparing-the-active-directory-schema-in-lync-server-2013"></a><span data-ttu-id="d5603-102">Подготовка схемы Active Directory в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d5603-102">Preparing the Active Directory schema in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d5603-103">_**Последнее изменение темы:** 2012-08-27_</span><span class="sxs-lookup"><span data-stu-id="d5603-103">_**Topic Last Modified:** 2012-08-27_</span></span>

<span data-ttu-id="d5603-104">Прежде чем приступить к подготовке доменных служб Active Directory, можно открыть файлы схемы в текстовом редакторе, например в блокноте Windows, или просмотреть все расширения схемы доменных служб Active Directory, которые будут изменены для Lync Server 2013, в текстовом редакторе, например в блокноте Windows, или на странице " [расширения схемы Active Directory, классы и атрибуты, используемые в Lync server 2013](lync-server-2013-active-directory-schema-extensions-classes-and-attributes-used-by-lync-server.md) .</span><span class="sxs-lookup"><span data-stu-id="d5603-104">Before you begin preparing Active Directory Domain Services, you can open the schema files by using a text editor, such as Windows Notepad, or see [Active Directory schema extensions, classes, and attributes used by Lync Server 2013](lync-server-2013-active-directory-schema-extensions-classes-and-attributes-used-by-lync-server.md) to review all the Active Directory Domain Services schema extensions that will be modified for Lync Server 2013.</span></span> <span data-ttu-id="d5603-105">Lync Server использует четыре файла схемы:</span><span class="sxs-lookup"><span data-stu-id="d5603-105">Lync Server uses four schema files:</span></span>

  - <span data-ttu-id="d5603-106">Екстерналсчема. ldf, который используется для взаимодействия с Microsoft Exchange Server</span><span class="sxs-lookup"><span data-stu-id="d5603-106">ExternalSchema.ldf, which is used for interoperability with Microsoft Exchange Server</span></span>

  - <span data-ttu-id="d5603-107">Серверсчема. ldf, который является основным файлом схемы Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d5603-107">ServerSchema.ldf, which is the primary Lync Server 2013 schema file</span></span>

  - <span data-ttu-id="d5603-108">BackCompatSchema.ldf, который используется для взаимодействия с какими-либо компонентами из предыдущих версий</span><span class="sxs-lookup"><span data-stu-id="d5603-108">BackCompatSchema.ldf, which is used for interoperability with any components from prior releases</span></span>

  - <span data-ttu-id="d5603-109">VersionSchema.ldf, который используется для получения информации о версии подготовленной схемы</span><span class="sxs-lookup"><span data-stu-id="d5603-109">VersionSchema.ldf, which is used for version information of the prepared schema</span></span>

<span data-ttu-id="d5603-110">Все файлы .ldf устанавливаются в ходе подготовки схемы независимо от того, выполняется ли перенос с предыдущей версии или чистая установка.</span><span class="sxs-lookup"><span data-stu-id="d5603-110">All .ldf files are installed during schema preparation, regardless of whether you are migrating from a previous release or performing a clean installation.</span></span> <span data-ttu-id="d5603-111">Эти файлы схемы устанавливаются в последовательности, показанной в предыдущем списке, и находятся в папке \\схемы\\поддержки на установочном носителе.</span><span class="sxs-lookup"><span data-stu-id="d5603-111">These schema files are installed in the sequence shown in the preceding list and are located in the \\Support\\schema folder on the installation media.</span></span>

<span data-ttu-id="d5603-112">Расширения схемы Lync Server реплицируются по всем доменам, что влияет на сетевой трафик.</span><span class="sxs-lookup"><span data-stu-id="d5603-112">The Lync Server schema extensions are replicated across all domains, which impacts network traffic.</span></span> <span data-ttu-id="d5603-113">Выполняйте подготовку схемы в то время, когда уровень использования сети является низким.</span><span class="sxs-lookup"><span data-stu-id="d5603-113">Run schema preparation at a time when network usage is low.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="d5603-114">Если вам нужно добавить поддержку Microsoft® Office Communicator Mobile 2007 R2 для Java и Microsoft® Office Communicator Mobile для Nokia 1,0 для мобильных клиентов в развертывание Lync Server 2013, необходимо подготовить схему Active Directory для Microsoft Office. Communications Server 2007 R2 во время установки Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d5603-114">If you need to add support for Microsoft® Office Communicator Mobile 2007 R2 for Java and Microsoft® Office Communicator Mobile for Nokia 1.0 mobile clients to your Lync Server 2013 deployment, you need to prepare the Active Directory schema for Microsoft Office Communications Server 2007 R2 during installation of Lync Server 2013.</span></span> <span data-ttu-id="d5603-115">Необходимое программное обеспечение и документация см <A href="https://go.microsoft.com/fwlink/p/?linkid=207172">https://go.microsoft.com/fwlink/p/?linkId=207172</A>.</span><span class="sxs-lookup"><span data-stu-id="d5603-115">For the necessary software and documentation, see <A href="https://go.microsoft.com/fwlink/p/?linkid=207172">https://go.microsoft.com/fwlink/p/?linkId=207172</A>.</span></span>



</div>

<div>

## <a name="adsi-edit"></a><span data-ttu-id="d5603-116">Редактор ADSI</span><span class="sxs-lookup"><span data-stu-id="d5603-116">ADSI Edit</span></span>

<span data-ttu-id="d5603-117">Редактор интерфейсов службы Active Directory (Active Directory Service Interfaces Editor — ADSI) — это средство администрирования AD DS, которое можно использовать для проверки подготовки схемы и репликации.</span><span class="sxs-lookup"><span data-stu-id="d5603-117">Active Directory Service Interfaces Editor (ADSI Edit) is an AD DS administration tool that you can use to verify schema preparation and replication.</span></span>

<span data-ttu-id="d5603-118">Редактор ADSI устанавливается по умолчанию при установке роли AD DS, чтобы сделать сервер контроллером домена.</span><span class="sxs-lookup"><span data-stu-id="d5603-118">ADSI Edit is installed by default when you install the AD DS role to make a server a domain controller.</span></span> <span data-ttu-id="d5603-119">Для Windows Server 2008 и Windows Server 2008 R2 в состав средств удаленного администрирования сервера (RSAT. msc) включено средство редактирования ADSI (adsiedit. msc).</span><span class="sxs-lookup"><span data-stu-id="d5603-119">For Windows Server 2008 and Windows Server 2008 R2, ADSI Edit (adsiedit.msc) is included with the Remote Server Administration Tools (RSAT).</span></span> <span data-ttu-id="d5603-120">Можно также установить RSAT на рядовые серверы или автономные серверы.</span><span class="sxs-lookup"><span data-stu-id="d5603-120">You can also install RSAT on domain member servers or stand-alone servers.</span></span> <span data-ttu-id="d5603-121">Пакет RSAT копируется на эти серверы по умолчанию при установке Windows, но их установка по умолчанию не выполняется.</span><span class="sxs-lookup"><span data-stu-id="d5603-121">The RSAT package is copied to these servers by default when you install Windows, but it is not installed by default.</span></span> <span data-ttu-id="d5603-122">Можно установить отдельные средства с помощью диспетчера серверов.</span><span class="sxs-lookup"><span data-stu-id="d5603-122">You install individual tools by using Server Manager.</span></span> <span data-ttu-id="d5603-123">Редактор ADSI входит в **средства администрирования ролей**, **средства доменных служб Active Directory** и **средства контроллера домена Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="d5603-123">ADSI Edit is included under **Role Administration Tools**, **Active Directory Domain Services Tools**, **Active Directory Domain Controller Tools**.</span></span>

<span data-ttu-id="d5603-124">При использовании Windows Server 2003 редактор ADSI входит в состав средств поддержки.</span><span class="sxs-lookup"><span data-stu-id="d5603-124">For Windows Server 2003, ADSI Edit is included with the Support Tools.</span></span> <span data-ttu-id="d5603-125">Средства поддержки доступны на компакт-диске Windows Server 2003 в папке " \\средства\\поддержки", или их можно загрузить с помощью средства поддержки Windows Server 2003 с пакетом обновления 2 32-разрядные [https://go.microsoft.com/fwlink/p/?linkId=125770](https://go.microsoft.com/fwlink/p/?linkid=125770)версии.</span><span class="sxs-lookup"><span data-stu-id="d5603-125">The Support Tools are available from the Windows Server 2003 CD in the \\SUPPORT\\TOOLS folder, or you can download them from “Windows Server 2003 Service Pack 2 32-bit Support Tools” at [https://go.microsoft.com/fwlink/p/?linkId=125770](https://go.microsoft.com/fwlink/p/?linkid=125770).</span></span> <span data-ttu-id="d5603-126">Инструкции по установке средств поддержки с компакт-диска продукта доступны в разделе "Установка средств поддержки Windows" [https://go.microsoft.com/fwlink/p/?linkId=125771](https://go.microsoft.com/fwlink/p/?linkid=125771).</span><span class="sxs-lookup"><span data-stu-id="d5603-126">Instructions for installing the Support Tools from the product CD are available from “Install Windows Support Tools” at [https://go.microsoft.com/fwlink/p/?linkId=125771](https://go.microsoft.com/fwlink/p/?linkid=125771).</span></span> <span data-ttu-id="d5603-127">Регистрация Adsiedit.dll выполняется автоматически при установке средств поддержки.</span><span class="sxs-lookup"><span data-stu-id="d5603-127">Adsiedit.dll is automatically registered when you install the support tools.</span></span> <span data-ttu-id="d5603-128">Однако, если вы скопировали файлы на компьютер, необходимо выполнить команду **regsvr32** для регистрации файла adsiedit.dll, прежде чем вы сможете запустить это средство.</span><span class="sxs-lookup"><span data-stu-id="d5603-128">If, however, you copied the files to your computer, you must run the **regsvr32** command to register the adsiedit.dll file before you can run the tool.</span></span>

</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="d5603-129">Содержание</span><span class="sxs-lookup"><span data-stu-id="d5603-129">In This Section</span></span>

  - [<span data-ttu-id="d5603-130">Выполнение подготовки схемы Active Directory в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d5603-130">Running Active Directory schema preparation in Lync Server 2013</span></span>](lync-server-2013-running-schema-preparation.md)

  - [<span data-ttu-id="d5603-131">Проверка репликации схемы Active Directory в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d5603-131">Verifying Active Directory schema replication in Lync Server 2013</span></span>](lync-server-2013-verifying-schema-replication.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="d5603-132">См. также</span><span class="sxs-lookup"><span data-stu-id="d5603-132">See Also</span></span>


[<span data-ttu-id="d5603-133">Подготовка леса для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d5603-133">Preparing the forest for Lync Server 2013</span></span>](lync-server-2013-preparing-the-forest.md)  
[<span data-ttu-id="d5603-134">Подготовка доменов для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d5603-134">Preparing domains for Lync Server 2013</span></span>](lync-server-2013-preparing-domains.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

