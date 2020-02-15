---
title: 'Lync Server 2013: Восстановление рядового сервера Enterprise Edition'
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
ms.openlocfilehash: c0643cf250e00b447bfac8a1b32c2a3038cff139
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42051091"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="restoring-an-enterprise-edition-member-server-in-lync-server-2013"></a><span data-ttu-id="27007-102">Восстановление рядового сервера Enterprise Edition в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="27007-102">Restoring an Enterprise Edition member server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="27007-103">_**Последнее изменение темы:** 2013-02-18_</span><span class="sxs-lookup"><span data-stu-id="27007-103">_**Topic Last Modified:** 2013-02-18_</span></span>

<span data-ttu-id="27007-104">Если сервер, на котором выполняется одна из указанных ниже ролей сервера, не удастся выполнить, выполните процедуру, описанную в этом разделе, для восстановления сервера.</span><span class="sxs-lookup"><span data-stu-id="27007-104">If a server running one of the following server roles fails, follow the procedure in this topic to restore the server.</span></span> <span data-ttu-id="27007-105">Если несколько серверов не отменяются независимо друг от друга, выполните процедуру для каждого сервера.</span><span class="sxs-lookup"><span data-stu-id="27007-105">If multiple servers fail independently, follow the procedure for each server.</span></span>

  - <span data-ttu-id="27007-106">Сервер переднего плана</span><span class="sxs-lookup"><span data-stu-id="27007-106">Front End Server</span></span>

  - <span data-ttu-id="27007-107">Сервер-посредник</span><span class="sxs-lookup"><span data-stu-id="27007-107">Mediation Server</span></span>

  - <span data-ttu-id="27007-108">Режиссер</span><span class="sxs-lookup"><span data-stu-id="27007-108">Director</span></span>

  - <span data-ttu-id="27007-109">Сервер сохраняемого чата</span><span class="sxs-lookup"><span data-stu-id="27007-109">Persistent Chat Server</span></span>

  - <span data-ttu-id="27007-110">Пограничный сервер</span><span class="sxs-lookup"><span data-stu-id="27007-110">Edge Server</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="27007-111">Перед началом восстановления рекомендуется использовать копию системы в виде образа.</span><span class="sxs-lookup"><span data-stu-id="27007-111">We recommend that you take an image copy of the system before you start restoration.</span></span> <span data-ttu-id="27007-112">Это изображение можно использовать в качестве точки отката, если в процессе восстановления что-то пойдет не так.</span><span class="sxs-lookup"><span data-stu-id="27007-112">You can use this image as a rollback point, in case something goes wrong during restoration.</span></span> <span data-ttu-id="27007-113">Вы можете использовать копию образа после установки операционной системы и SQL Server, а также для восстановления или повторной регистрации сертификатов.</span><span class="sxs-lookup"><span data-stu-id="27007-113">You might want to take the image copy after you install the operating system and SQL Server, and restore or reenroll the certificates.</span></span>



</div>

<div>

## <a name="to-restore-a-member-server"></a><span data-ttu-id="27007-114">Восстановление рядового сервера</span><span class="sxs-lookup"><span data-stu-id="27007-114">To restore a member server</span></span>

1.  <span data-ttu-id="27007-115">Начните с чистого или нового сервера с таким же полным доменным именем (FQDN) в качестве сервера, на котором произошел сбой, установите операционную систему, а затем восстановите или повторно зарегистрируйте сертификаты.</span><span class="sxs-lookup"><span data-stu-id="27007-115">Start with a clean or new server that has the same fully qualified domain name (FQDN) as the failed server, install the operating system, and then restore or reenroll the certificates.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="27007-116">Для выполнения этого действия следуйте процедурам развертывания сервера в Организации.</span><span class="sxs-lookup"><span data-stu-id="27007-116">Follow your organization's server deployment procedures to perform this step.</span></span>

    
    </div>

2.  <span data-ttu-id="27007-117">Из учетной записи пользователя, входящей в группу RTCUniversalServerAdmins, войдите на сервер, который вы восстанавливаете.</span><span class="sxs-lookup"><span data-stu-id="27007-117">From a user account that is a member of the RTCUniversalServerAdmins group, log on to the server that you are restoring.</span></span>

3.  <span data-ttu-id="27007-118">Перейдите к папке установки Lync Server или носителю и запустите мастер развертывания Lync Server, расположенный в \\программе установки\\amd64\\. exe.</span><span class="sxs-lookup"><span data-stu-id="27007-118">Browse to the Lync Server installation folder or media, and start the Lync Server Deployment Wizard located at \\setup\\amd64\\Setup.exe.</span></span>

4.  <span data-ttu-id="27007-119">Следуйте указаниям мастера развертывания, чтобы выполнить следующие действия:</span><span class="sxs-lookup"><span data-stu-id="27007-119">Follow the Deployment Wizard to do the following:</span></span>
    
    1.  <span data-ttu-id="27007-120">Выполните **Шаг 1: установите локальное хранилище конфигураций** , чтобы установить локальные файлы конфигурации.</span><span class="sxs-lookup"><span data-stu-id="27007-120">Run **Step 1: Install Local Configuration Store** to install the local configuration files.</span></span>
    
    2.  <span data-ttu-id="27007-121">Выполните **Шаг 2: Установка или удаление компонентов Lync Server** для установки роли сервера Lync Server.</span><span class="sxs-lookup"><span data-stu-id="27007-121">Run **Step 2: Setup or Remove Lync Server Components** to install the Lync Server server role.</span></span>
    
    3.  <span data-ttu-id="27007-122">Выполните **Шаг 3: запрос, установка или назначение сертификатов** для назначения сертификатов.</span><span class="sxs-lookup"><span data-stu-id="27007-122">Run **Step 3: Request, Install or Assign Certificates** to assign the certificates.</span></span>
    
    4.  <span data-ttu-id="27007-123">Выполните **Шаг 4: запуск служб** для запуска служб на сервере.</span><span class="sxs-lookup"><span data-stu-id="27007-123">Run **Step 4: Start Services** to start services on the server.</span></span>
    
    <span data-ttu-id="27007-124">Для получения дополнительных сведений о запуске мастера развертывания обратитесь к документации по развертыванию для восстанавливаемой роли сервера.</span><span class="sxs-lookup"><span data-stu-id="27007-124">For details about running the Deployment Wizard, see the Deployment documentation for the server role that you are restoring.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

