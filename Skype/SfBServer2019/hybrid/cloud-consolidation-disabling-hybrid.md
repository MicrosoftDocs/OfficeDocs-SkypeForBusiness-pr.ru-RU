---
title: Отключить гибридный для выполнения миграции в облако
ms.author: crowe
author: crowe
manager: serdars
ms.reviewer: bjwhalen
ms.topic: article
ms.service:
- skype-for-business-online
- msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
description: В этом приложении включает в себя описанные далее действия для отключения гибридного как часть облака консолидации для групп и Скайп для бизнеса.
ms.openlocfilehash: 03c38a4482d9a0bd6e728138b3d856b552e4754a
ms.sourcegitcommit: 4dac1994b829d7a7aefc3c003eec998e011c1bd3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/13/2018
ms.locfileid: "27247712"
---
# <a name="disable-hybrid-to-complete-migration-to-the-cloud"></a><span data-ttu-id="e68d8-103">Отключить гибридный для выполнения миграции в облако</span><span class="sxs-lookup"><span data-stu-id="e68d8-103">Disable hybrid to complete migration to the cloud</span></span>

<span data-ttu-id="e68d8-104">После перемещения всех пользователей из локального с облаком, можно выводить из эксплуатации Скайп локальной по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="e68d8-104">After you have moved all users from on-premises to the cloud, you can decommission the on-premises Skype for Business deployment.</span></span> <span data-ttu-id="e68d8-105">Помимо удаления оборудования, важным этапом является логически отделения, локальное развертывание из Office 365, отключив гибридного.</span><span class="sxs-lookup"><span data-stu-id="e68d8-105">Aside from removing any hardware, a critical step is to logically separate that on-premises deployment from Office 365 by disabling hybrid.</span></span> <span data-ttu-id="e68d8-106">Отключение гибридного состоит из шагов.</span><span class="sxs-lookup"><span data-stu-id="e68d8-106">Disabling hybrid consists of 3 steps:</span></span>

1. <span data-ttu-id="e68d8-107">Обновление записей DNS для указания на Office 365.</span><span class="sxs-lookup"><span data-stu-id="e68d8-107">Update DNS records to point to Office 365.</span></span>
2. <span data-ttu-id="e68d8-108">Отключение разделенного домена в Office 365 для клиентов.</span><span class="sxs-lookup"><span data-stu-id="e68d8-108">Disable split domain in the Office 365 tenant.</span></span>
3. <span data-ttu-id="e68d8-109">Отключение возможности на prem общаться с Office 365.</span><span class="sxs-lookup"><span data-stu-id="e68d8-109">Disable ability in on-prem to communicate with Office 365.</span></span>


<span data-ttu-id="e68d8-110">Эти шаги должны выполняться вместе как одно целое.</span><span class="sxs-lookup"><span data-stu-id="e68d8-110">These steps should be done together as a unit.</span></span> <span data-ttu-id="e68d8-111">Подробные сведения приведены ниже.</span><span class="sxs-lookup"><span data-stu-id="e68d8-111">Details are provided below.</span></span>

> [!Note] 
> <span data-ttu-id="e68d8-112">В редких случаях изменение DNS из указывают на собственных Office 365 для вашей организации может стать причиной федерации с другими организациями перестает работать до того времени, что другие организации обновляет их конфигурации федерации:</span><span class="sxs-lookup"><span data-stu-id="e68d8-112">In rare cases, changing DNS from pointing on premises to Office 365 for your organization may cause federation with some other organizations to stop working until that other organization updates their federation configuration:</span></span><ul><li>
<span data-ttu-id="e68d8-113">Любой федеративными организациями, в которых используется старая модель прямая Федерация (также известной как разрешенным сервером партнера) потребуется обновить их записи разрешенных доменов для своей организации удалить полное доменное имя прокси-сервера.</span><span class="sxs-lookup"><span data-stu-id="e68d8-113">Any federated organizations that are using the older Direct Federation model (also known as Allowed Partner Server) will need to update their allowed domain entries for their organization to remove the proxy FQDN.</span></span> <span data-ttu-id="e68d8-114">В этой модели прежних версий федерации не основано на DNS SRV-записи, поэтому такая настройка станут устаревший после перемещения вашей организации в облако.</span><span class="sxs-lookup"><span data-stu-id="e68d8-114">This legacy federation model is not based on DNS SRV records, so such a configuration will become out of date once your organization moves to the cloud.</span></span> </li><li><span data-ttu-id="e68d8-115">Любой федеративной организации, для которого не включен поставщика услуг размещения для sipfed.online.lync. <span>com потребуется обновить их конфигурации для включения.</span><span class="sxs-lookup"><span data-stu-id="e68d8-115">Any federated organization that does not have an enabled hosting provider for sipfed.online.lync.<span>com will need to update their configuration to enable that.</span></span> <span data-ttu-id="e68d8-116">В этом случае возможно только в том случае, если федеративной организации исключительно на локальном и никогда не имеет федеративных с гибридной или интерактивного клиента.</span><span class="sxs-lookup"><span data-stu-id="e68d8-116">This situation is only possible if the federated organization is purely on premises and has never federated with any hybrid or online tenant.</span></span> <span data-ttu-id="e68d8-117">В этом случае федерацию с эти организации не будет работать, пока они включить их поставщика услуг размещения.</span><span class="sxs-lookup"><span data-stu-id="e68d8-117">In such a case, federation with these organizations will not work until they enable their hosting provider.</span></span></li></ul><span data-ttu-id="e68d8-118">Если предполагается, что федеративных партнеров могут использовать прямая Федерация и федеративный с любыми Интернет-версия или организации гибридного, мы рекомендуем отправки, обмена данными об этом при подготовке к выполнить миграцию в облако.</span><span class="sxs-lookup"><span data-stu-id="e68d8-118">If you suspect that any of your federated partners may be using Direct Federation or have federated with any online or hybrid organization, we suggest you send them a communication about this as you prepare to complete your migration to the cloud.</span></span>

1.  <span data-ttu-id="e68d8-119">*Обновите DNS на Office 365.*</span><span class="sxs-lookup"><span data-stu-id="e68d8-119">*Update DNS to point to Office 365.*</span></span>
<span data-ttu-id="e68d8-120">Внешний DNS-сервер в организации, для локальной организации необходимо обновить, чтобы Скайп для бизнес-записей выберите пункт Office 365 вместо локального развертывания.</span><span class="sxs-lookup"><span data-stu-id="e68d8-120">The organization’s external DNS for the on-premises organization needs to be updated so that Skype for Business records point to Office 365 instead of the on-premises deployment.</span></span> <span data-ttu-id="e68d8-121">А именно:</span><span class="sxs-lookup"><span data-stu-id="e68d8-121">Specifically:</span></span>

    |<span data-ttu-id="e68d8-122">Тип записи</span><span class="sxs-lookup"><span data-stu-id="e68d8-122">Record type</span></span>|<span data-ttu-id="e68d8-123">Имя</span><span class="sxs-lookup"><span data-stu-id="e68d8-123">Name</span></span>|<span data-ttu-id="e68d8-124">TTL</span><span class="sxs-lookup"><span data-stu-id="e68d8-124">TTL</span></span>|<span data-ttu-id="e68d8-125">Значение</span><span class="sxs-lookup"><span data-stu-id="e68d8-125">Value</span></span>|
    |---|---|---|---|
    |<span data-ttu-id="e68d8-126">SRV</span><span class="sxs-lookup"><span data-stu-id="e68d8-126">SRV</span></span>|<span data-ttu-id="e68d8-127">_sipfederationtls._tcp</span><span class="sxs-lookup"><span data-stu-id="e68d8-127">_sipfederationtls._tcp</span></span>|<span data-ttu-id="e68d8-128">3600</span><span class="sxs-lookup"><span data-stu-id="e68d8-128">3600</span></span>|<span data-ttu-id="e68d8-129">100 1 5061 sipfed.online.lync. <span>com</span><span class="sxs-lookup"><span data-stu-id="e68d8-129">100 1 5061 sipfed.online.lync.<span>com</span></span>|
    |<span data-ttu-id="e68d8-130">SRV</span><span class="sxs-lookup"><span data-stu-id="e68d8-130">SRV</span></span>|<span data-ttu-id="e68d8-131">_sip._tls</span><span class="sxs-lookup"><span data-stu-id="e68d8-131">_sip._tls</span></span>|<span data-ttu-id="e68d8-132">3600</span><span class="sxs-lookup"><span data-stu-id="e68d8-132">3600</span></span>|<span data-ttu-id="e68d8-133">100 1 443 sipdir.online.lync. <span>com</span><span class="sxs-lookup"><span data-stu-id="e68d8-133">100 1 443 sipdir.online.lync.<span>com</span></span>|
    |<span data-ttu-id="e68d8-134">CNAME</span><span class="sxs-lookup"><span data-stu-id="e68d8-134">CNAME</span></span>| <span data-ttu-id="e68d8-135">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="e68d8-135">lyncdiscover</span></span>|   <span data-ttu-id="e68d8-136">3600</span><span class="sxs-lookup"><span data-stu-id="e68d8-136">3600</span></span>|   <span data-ttu-id="e68d8-137">webdir.Online.Lync. <span>com</span><span class="sxs-lookup"><span data-stu-id="e68d8-137">webdir.online.lync.<span>com</span></span>|
    |<span data-ttu-id="e68d8-138">CNAME</span><span class="sxs-lookup"><span data-stu-id="e68d8-138">CNAME</span></span>| <span data-ttu-id="e68d8-139">SIP-</span><span class="sxs-lookup"><span data-stu-id="e68d8-139">sip</span></span>|    <span data-ttu-id="e68d8-140">3600</span><span class="sxs-lookup"><span data-stu-id="e68d8-140">3600</span></span>|   <span data-ttu-id="e68d8-141">sipdir.Online.Lync. <span>com</span><span class="sxs-lookup"><span data-stu-id="e68d8-141">sipdir.online.lync.<span>com</span></span>|
    |<span data-ttu-id="e68d8-142">CNAME</span><span class="sxs-lookup"><span data-stu-id="e68d8-142">CNAME</span></span>| <span data-ttu-id="e68d8-143">провести</span><span class="sxs-lookup"><span data-stu-id="e68d8-143">meet</span></span>|   <span data-ttu-id="e68d8-144">3600</span><span class="sxs-lookup"><span data-stu-id="e68d8-144">3600</span></span>|   <span data-ttu-id="e68d8-145">webdir.Online.Lync. <span>com</span><span class="sxs-lookup"><span data-stu-id="e68d8-145">webdir.online.lync.<span>com</span></span>|
    |<span data-ttu-id="e68d8-146">CNAME</span><span class="sxs-lookup"><span data-stu-id="e68d8-146">CNAME</span></span>| <span data-ttu-id="e68d8-147">Dialin</span><span class="sxs-lookup"><span data-stu-id="e68d8-147">dialin</span></span>  |<span data-ttu-id="e68d8-148">3600</span><span class="sxs-lookup"><span data-stu-id="e68d8-148">3600</span></span>|  <span data-ttu-id="e68d8-149">webdir.Online.Lync. <span>com</span><span class="sxs-lookup"><span data-stu-id="e68d8-149">webdir.online.lync.<span>com</span></span>|

2.  <span data-ttu-id="e68d8-150">*Отключите общее адресное пространство SIP в клиента Office 365.*</span><span class="sxs-lookup"><span data-stu-id="e68d8-150">*Disable shared SIP address space in Office 365 tenant.*</span></span>
<span data-ttu-id="e68d8-151">Ниже команды необходимо выполнить из Скайп для окна Online PowerShell бизнеса.</span><span class="sxs-lookup"><span data-stu-id="e68d8-151">The command below needs to be done from a Skype for Business Online PowerShell window.</span></span>

    `Set-CsTenantFederationConfiguration -SharedSipAddressSpace $false`
 
3.  <span data-ttu-id="e68d8-152">*Отключение возможности на prem общаться с Office 365.*</span><span class="sxs-lookup"><span data-stu-id="e68d8-152">*Disable ability in on-prem to communicate with Office 365.*</span></span>  
<span data-ttu-id="e68d8-153">Также необходимо выполнить из окна PowerShell в локальной приведенной ниже команды.</span><span class="sxs-lookup"><span data-stu-id="e68d8-153">The command below needs to be done from an on-premises PowerShell window.</span></span>  <span data-ttu-id="e68d8-154">Если ранее были импортированы Скайп для бизнеса в Интернет сеанса, запустите новый Скайп для сеанса PowerShell бизнеса.</span><span class="sxs-lookup"><span data-stu-id="e68d8-154">If you have previously imported a Skype for Business Online session, start a new Skype for Business PowerShell session.</span></span>

    `Get-CsHostingProvider|Set-CsHostingProvider -Enabled $false`

## <a name="see-also"></a><span data-ttu-id="e68d8-155">См. также</span><span class="sxs-lookup"><span data-stu-id="e68d8-155">See also</span></span>

[<span data-ttu-id="e68d8-156">Консолидация облако для групп и Скайп для бизнеса</span><span class="sxs-lookup"><span data-stu-id="e68d8-156">Cloud Consolidation for Teams and Skype for Business</span></span>](cloud-consolidation.md)