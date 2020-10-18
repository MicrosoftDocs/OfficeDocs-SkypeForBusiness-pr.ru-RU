---
title: 'Lync Server 2013: Восстановление рядового сервера Enterprise Edition'
description: 'Lync Server 2013: Восстановление рядового сервера Enterprise Edition.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Restoring an Enterprise Edition member server
ms:assetid: d960b19c-2104-4719-b736-0d940f254d42
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202191(v=OCS.15)
ms:contentKeyID: 51541523
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4f9838f030205d92988e185798d982f835122c9f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48576055"
---
# <a name="restoring-an-enterprise-edition-member-server-in-lync-server-2013"></a><span data-ttu-id="012dd-103">Восстановление рядового сервера Enterprise Edition в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="012dd-103">Restoring an Enterprise Edition member server in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="012dd-104">_**Последнее изменение темы:** 2013-02-18_</span><span class="sxs-lookup"><span data-stu-id="012dd-104">_**Topic Last Modified:** 2013-02-18_</span></span>

<span data-ttu-id="012dd-105">Если сервер, на котором выполняется одна из указанных ниже ролей сервера, не удастся выполнить, выполните процедуру, описанную в этом разделе, для восстановления сервера.</span><span class="sxs-lookup"><span data-stu-id="012dd-105">If a server running one of the following server roles fails, follow the procedure in this topic to restore the server.</span></span> <span data-ttu-id="012dd-106">Если несколько серверов не отменяются независимо друг от друга, выполните процедуру для каждого сервера.</span><span class="sxs-lookup"><span data-stu-id="012dd-106">If multiple servers fail independently, follow the procedure for each server.</span></span>

  - <span data-ttu-id="012dd-107">Сервер переднего плана</span><span class="sxs-lookup"><span data-stu-id="012dd-107">Front End Server</span></span>

  - <span data-ttu-id="012dd-108">Сервер-посредник</span><span class="sxs-lookup"><span data-stu-id="012dd-108">Mediation Server</span></span>

  - <span data-ttu-id="012dd-109">Директор</span><span class="sxs-lookup"><span data-stu-id="012dd-109">Director</span></span>

  - <span data-ttu-id="012dd-110">Сервер сохраняемого чата</span><span class="sxs-lookup"><span data-stu-id="012dd-110">Persistent Chat Server</span></span>

  - <span data-ttu-id="012dd-111">Пограничный сервер</span><span class="sxs-lookup"><span data-stu-id="012dd-111">Edge Server</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="012dd-112">Перед началом восстановления рекомендуется использовать копию системы в виде образа.</span><span class="sxs-lookup"><span data-stu-id="012dd-112">We recommend that you take an image copy of the system before you start restoration.</span></span> <span data-ttu-id="012dd-113">Это изображение можно использовать в качестве точки отката, если в процессе восстановления что-то пойдет не так.</span><span class="sxs-lookup"><span data-stu-id="012dd-113">You can use this image as a rollback point, in case something goes wrong during restoration.</span></span> <span data-ttu-id="012dd-114">Вы можете использовать копию образа после установки операционной системы и SQL Server, а также для восстановления или повторной регистрации сертификатов.</span><span class="sxs-lookup"><span data-stu-id="012dd-114">You might want to take the image copy after you install the operating system and SQL Server, and restore or reenroll the certificates.</span></span>



</div>

<div>

## <a name="to-restore-a-member-server"></a><span data-ttu-id="012dd-115">Восстановление рядового сервера</span><span class="sxs-lookup"><span data-stu-id="012dd-115">To restore a member server</span></span>

1.  <span data-ttu-id="012dd-116">Начните с чистого или нового сервера с таким же полным доменным именем (FQDN) в качестве сервера, на котором произошел сбой, установите операционную систему, а затем восстановите или повторно зарегистрируйте сертификаты.</span><span class="sxs-lookup"><span data-stu-id="012dd-116">Start with a clean or new server that has the same fully qualified domain name (FQDN) as the failed server, install the operating system, and then restore or reenroll the certificates.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="012dd-117">Для выполнения этого действия следуйте процедурам развертывания сервера в Организации.</span><span class="sxs-lookup"><span data-stu-id="012dd-117">Follow your organization's server deployment procedures to perform this step.</span></span>

    
    </div>

2.  <span data-ttu-id="012dd-118">Из учетной записи пользователя, входящей в группу RTCUniversalServerAdmins, войдите на сервер, который вы восстанавливаете.</span><span class="sxs-lookup"><span data-stu-id="012dd-118">From a user account that is a member of the RTCUniversalServerAdmins group, log on to the server that you are restoring.</span></span>

3.  <span data-ttu-id="012dd-119">Перейдите к папке установки Lync Server или носителю и запустите мастер развертывания Lync Server, расположенный при \\ установке \\ amd64 \\Setup.exe.</span><span class="sxs-lookup"><span data-stu-id="012dd-119">Browse to the Lync Server installation folder or media, and start the Lync Server Deployment Wizard located at \\setup\\amd64\\Setup.exe.</span></span>

4.  <span data-ttu-id="012dd-120">Следуйте указаниям мастера развертывания, чтобы выполнить следующие действия:</span><span class="sxs-lookup"><span data-stu-id="012dd-120">Follow the Deployment Wizard to do the following:</span></span>
    
    1.  <span data-ttu-id="012dd-121">Выполните **Шаг 1: установите локальное хранилище конфигураций** , чтобы установить локальные файлы конфигурации.</span><span class="sxs-lookup"><span data-stu-id="012dd-121">Run **Step 1: Install Local Configuration Store** to install the local configuration files.</span></span>
    
    2.  <span data-ttu-id="012dd-122">Выполните **Шаг 2: Установка или удаление компонентов Lync Server** для установки роли сервера Lync Server.</span><span class="sxs-lookup"><span data-stu-id="012dd-122">Run **Step 2: Setup or Remove Lync Server Components** to install the Lync Server server role.</span></span>
    
    3.  <span data-ttu-id="012dd-123">Выполните **Шаг 3: запрос, установка или назначение сертификатов** для назначения сертификатов.</span><span class="sxs-lookup"><span data-stu-id="012dd-123">Run **Step 3: Request, Install or Assign Certificates** to assign the certificates.</span></span>
    
    4.  <span data-ttu-id="012dd-124">Выполните **Шаг 4: запуск служб** для запуска служб на сервере.</span><span class="sxs-lookup"><span data-stu-id="012dd-124">Run **Step 4: Start Services** to start services on the server.</span></span>
    
    <span data-ttu-id="012dd-125">Для получения дополнительных сведений о запуске мастера развертывания обратитесь к документации по развертыванию для восстанавливаемой роли сервера.</span><span class="sxs-lookup"><span data-stu-id="012dd-125">For details about running the Deployment Wizard, see the Deployment documentation for the server role that you are restoring.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

