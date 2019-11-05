---
title: Отключение гибридной среды для завершения миграции в облако
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
ms.topic: article
ms.prod: skype-for-business-itpro
search.appverid: MET150
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
audience: ITPro
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
description: В этом приложении содержатся подробные инструкции по отключению гибридной среды в составе облачной консолидации для Teams и Skype для бизнеса.
ms.openlocfilehash: d441d9fcc5e4f2cec495efabdbea423eaaec882c
ms.sourcegitcommit: 7920c47eb73e665dad4bf7214b28541d357bce25
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/04/2019
ms.locfileid: "37962061"
---
# <a name="disable-hybrid-to-complete-migration-to-the-cloud"></a><span data-ttu-id="6afff-103">Отключение гибридной среды для завершения миграции в облако</span><span class="sxs-lookup"><span data-stu-id="6afff-103">Disable hybrid to complete migration to the cloud</span></span>

<span data-ttu-id="6afff-104">После перемещения всех пользователей из локальной среды в облако можно списать локальное развертывание Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="6afff-104">After you have moved all users from on-premises to the cloud, you can decommission the on-premises Skype for Business deployment.</span></span> <span data-ttu-id="6afff-105">Помимо удаления какого-либо оборудования, критически важный шаг состоит в том, чтобы логически отделить локальное развертывание от Office 365, отключив гибридную среду.</span><span class="sxs-lookup"><span data-stu-id="6afff-105">Aside from removing any hardware, a critical step is to logically separate that on-premises deployment from Office 365 by disabling hybrid.</span></span> <span data-ttu-id="6afff-106">Отключение гибридной среды состоит из трех этапов:</span><span class="sxs-lookup"><span data-stu-id="6afff-106">Disabling hybrid consists of 3 steps:</span></span>

1. <span data-ttu-id="6afff-107">Обновление записей DNS для ссылки на Office 365.</span><span class="sxs-lookup"><span data-stu-id="6afff-107">Update DNS records to point to Office 365.</span></span>

2. <span data-ttu-id="6afff-108">Отключите разделенный домен в клиенте Office 365.</span><span class="sxs-lookup"><span data-stu-id="6afff-108">Disable split domain in the Office 365 tenant.</span></span>

3. <span data-ttu-id="6afff-109">Отключение возможности локального подключения к Office 365.</span><span class="sxs-lookup"><span data-stu-id="6afff-109">Disable the ability in on-premises to communicate with Office 365.</span></span>

<span data-ttu-id="6afff-110">Эти действия необходимо выполнить вместе как единое целое.</span><span class="sxs-lookup"><span data-stu-id="6afff-110">These steps should be done together as a unit.</span></span> <span data-ttu-id="6afff-111">Подробные сведения приведены ниже.</span><span class="sxs-lookup"><span data-stu-id="6afff-111">Details are provided below.</span></span> <span data-ttu-id="6afff-112">Кроме того, предоставляются рекомендации по управлению номерами телефонов для мигрировавших пользователей, когда локальное развертывание отключено.</span><span class="sxs-lookup"><span data-stu-id="6afff-112">In addition, guidelines are provided for managing phone numbers for migrated users once the on-premises deployment is disconnected.</span></span>

> [!Note] 
> <span data-ttu-id="6afff-113">В редких случаях изменение DNS, направленное на Office 365 для вашей организации, может привести к прекращению работы Федерации с другими организациями, пока другая организация не обновит свою конфигурацию Федерации:</span><span class="sxs-lookup"><span data-stu-id="6afff-113">In rare cases, changing DNS from pointing on premises to Office 365 for your organization may cause federation with some other organizations to stop working until that other organization updates their federation configuration:</span></span><ul><li>
<span data-ttu-id="6afff-114">Для всех федеративных организаций, использующих старую прямую модель Федерации (также известное как разрешенный сервер-партнер), необходимо обновить записи разрешенных доменов для своей организации, чтобы удалить полное доменное имя прокси-сервера.</span><span class="sxs-lookup"><span data-stu-id="6afff-114">Any federated organizations that are using the older Direct Federation model (also known as Allowed Partner Server) will need to update their allowed domain entries for their organization to remove the proxy FQDN.</span></span> <span data-ttu-id="6afff-115">Эта устаревшая модель Федерации не основана на записях DNS SRV, поэтому такая конфигурация станет устаревшей после того, как ваша организация перейдет в облако.</span><span class="sxs-lookup"><span data-stu-id="6afff-115">This legacy federation model is not based on DNS SRV records, so such a configuration will become out of date once your organization moves to the cloud.</span></span> </li><li><span data-ttu-id="6afff-116">Любая федеративная организация, у которой нет включенного поставщика услуг хостинга для sipfed. Online. Lync. <span>com необходимо обновить конфигурацию, чтобы она была включена.</span><span class="sxs-lookup"><span data-stu-id="6afff-116">Any federated organization that does not have an enabled hosting provider for sipfed.online.lync.<span>com will need to update their configuration to enable that.</span></span> <span data-ttu-id="6afff-117">Такая ситуация возможна только в том случае, если федеративная организация является исключительно локальной и никогда не участвует в гибридном или интернет-клиенте.</span><span class="sxs-lookup"><span data-stu-id="6afff-117">This situation is only possible if the federated organization is purely on premises and has never federated with any hybrid or online tenant.</span></span> <span data-ttu-id="6afff-118">В этом случае Федерация с этими организациями не будет работать, пока не включит их поставщика услуг хостинга.</span><span class="sxs-lookup"><span data-stu-id="6afff-118">In such a case, federation with these organizations will not work until they enable their hosting provider.</span></span></li></ul><span data-ttu-id="6afff-119">Если вы подозреваете, что любой из федеративных партнеров может использовать прямую федерацию или иметь федеративные связи с любой локальной или гибридной организацией, мы рекомендуем вам отправить им информацию о том, как вы готовитесь к выполнению миграции в облако.</span><span class="sxs-lookup"><span data-stu-id="6afff-119">If you suspect that any of your federated partners may be using Direct Federation or have federated with any online or hybrid organization, we suggest you send them a communication about this as you prepare to complete your migration to the cloud.</span></span>

1.  <span data-ttu-id="6afff-120">*Обновите DNS, чтобы указать на Office 365.*</span><span class="sxs-lookup"><span data-stu-id="6afff-120">*Update DNS to point to Office 365.*</span></span>
<span data-ttu-id="6afff-121">Необходимо обновить внешнюю DNS организации для локальной организации, чтобы записи Skype для бизнеса направляться на Office 365, а не в локальное развертывание.</span><span class="sxs-lookup"><span data-stu-id="6afff-121">The organization’s external DNS for the on-premises organization needs to be updated so that Skype for Business records point to Office 365 instead of the on-premises deployment.</span></span> <span data-ttu-id="6afff-122">Это означает следующее:</span><span class="sxs-lookup"><span data-stu-id="6afff-122">Specifically:</span></span>

    |<span data-ttu-id="6afff-123">Тип записи</span><span class="sxs-lookup"><span data-stu-id="6afff-123">Record type</span></span>|<span data-ttu-id="6afff-124">Имя</span><span class="sxs-lookup"><span data-stu-id="6afff-124">Name</span></span>|<span data-ttu-id="6afff-125">TTL (Срок жизни)</span><span class="sxs-lookup"><span data-stu-id="6afff-125">TTL</span></span>|<span data-ttu-id="6afff-126">Value (Значение)</span><span class="sxs-lookup"><span data-stu-id="6afff-126">Value</span></span>|
    |---|---|---|---|
    |<span data-ttu-id="6afff-127">SRV</span><span class="sxs-lookup"><span data-stu-id="6afff-127">SRV</span></span>|<span data-ttu-id="6afff-128">_sipfederationtls. _tcp</span><span class="sxs-lookup"><span data-stu-id="6afff-128">_sipfederationtls._tcp</span></span>|<span data-ttu-id="6afff-129">3600</span><span class="sxs-lookup"><span data-stu-id="6afff-129">3600</span></span>|<span data-ttu-id="6afff-130">100 1 5061 sipfed. Online. Lync. <span>com-</span><span class="sxs-lookup"><span data-stu-id="6afff-130">100 1 5061 sipfed.online.lync.<span>com</span></span>|
    |<span data-ttu-id="6afff-131">SRV</span><span class="sxs-lookup"><span data-stu-id="6afff-131">SRV</span></span>|<span data-ttu-id="6afff-132">_sip._tls</span><span class="sxs-lookup"><span data-stu-id="6afff-132">_sip._tls</span></span>|<span data-ttu-id="6afff-133">3600</span><span class="sxs-lookup"><span data-stu-id="6afff-133">3600</span></span>|<span data-ttu-id="6afff-134">100 1 443 sipdir. Online. Lync. <span>com-</span><span class="sxs-lookup"><span data-stu-id="6afff-134">100 1 443 sipdir.online.lync.<span>com</span></span>|
    |<span data-ttu-id="6afff-135">CNAME</span><span class="sxs-lookup"><span data-stu-id="6afff-135">CNAME</span></span>| <span data-ttu-id="6afff-136">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="6afff-136">lyncdiscover</span></span>|   <span data-ttu-id="6afff-137">3600</span><span class="sxs-lookup"><span data-stu-id="6afff-137">3600</span></span>|   <span data-ttu-id="6afff-138">webdir. Online. Lync. <span>com-</span><span class="sxs-lookup"><span data-stu-id="6afff-138">webdir.online.lync.<span>com</span></span>|
    |<span data-ttu-id="6afff-139">CNAME</span><span class="sxs-lookup"><span data-stu-id="6afff-139">CNAME</span></span>| <span data-ttu-id="6afff-140">sip</span><span class="sxs-lookup"><span data-stu-id="6afff-140">sip</span></span>|    <span data-ttu-id="6afff-141">3600</span><span class="sxs-lookup"><span data-stu-id="6afff-141">3600</span></span>|   <span data-ttu-id="6afff-142">sipdir. Online. Lync. <span>com-</span><span class="sxs-lookup"><span data-stu-id="6afff-142">sipdir.online.lync.<span>com</span></span>|
    |<span data-ttu-id="6afff-143">CNAME</span><span class="sxs-lookup"><span data-stu-id="6afff-143">CNAME</span></span>| <span data-ttu-id="6afff-144">Согласно</span><span class="sxs-lookup"><span data-stu-id="6afff-144">meet</span></span>|   <span data-ttu-id="6afff-145">3600</span><span class="sxs-lookup"><span data-stu-id="6afff-145">3600</span></span>|   <span data-ttu-id="6afff-146">webdir. Online. Lync. <span>com-</span><span class="sxs-lookup"><span data-stu-id="6afff-146">webdir.online.lync.<span>com</span></span>|
    |<span data-ttu-id="6afff-147">CNAME</span><span class="sxs-lookup"><span data-stu-id="6afff-147">CNAME</span></span>| <span data-ttu-id="6afff-148">Dialin</span><span class="sxs-lookup"><span data-stu-id="6afff-148">dialin</span></span>  |<span data-ttu-id="6afff-149">3600</span><span class="sxs-lookup"><span data-stu-id="6afff-149">3600</span></span>|  <span data-ttu-id="6afff-150">webdir. Online. Lync. <span>com-</span><span class="sxs-lookup"><span data-stu-id="6afff-150">webdir.online.lync.<span>com</span></span>|

2.  <span data-ttu-id="6afff-151">*Отключите общее адресное пространство SIP в клиенте Office 365.*</span><span class="sxs-lookup"><span data-stu-id="6afff-151">*Disable shared SIP address space in Office 365 tenant.*</span></span>
<span data-ttu-id="6afff-152">Приведенная ниже команда должна быть выполнена в окне PowerShell Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="6afff-152">The command below needs to be done from a Skype for Business Online PowerShell window.</span></span>

    ```
    Set-CsTenantFederationConfiguration -SharedSipAddressSpace $false
    ```
 
3.  <span data-ttu-id="6afff-153">*Отключение возможности локального подключения к Office 365.*</span><span class="sxs-lookup"><span data-stu-id="6afff-153">*Disable ability in on-prem to communicate with Office 365.*</span></span>  
<span data-ttu-id="6afff-154">Приведенная ниже команда должна быть выполнена из локального окна PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6afff-154">The command below needs to be done from an on-premises PowerShell window.</span></span>  <span data-ttu-id="6afff-155">Если вы ранее импортировали сеанс Skype для бизнеса Online, запустите новый сеанс PowerShell для Skype для бизнеса следующим образом:</span><span class="sxs-lookup"><span data-stu-id="6afff-155">If you have previously imported a Skype for Business Online session, start a new Skype for Business PowerShell session as follows:</span></span>

```
    Get-CsHostingProvider|Set-CsHostingProvider -Enabled $false
```

### <a name="manage-phone-numbers-for-users-who-were-migrated-from-on-premises"></a><span data-ttu-id="6afff-156">Управление номерами телефонов для пользователей, которые были перенесены из локальной организации</span><span class="sxs-lookup"><span data-stu-id="6afff-156">Manage phone numbers for users who were migrated from on-premises</span></span>

<span data-ttu-id="6afff-157">Администраторы могут управлять пользователями, которые ранее были перемещены с локального сервера Skype для бизнеса в облако, даже после того, как локальное развертывание будет списано.</span><span class="sxs-lookup"><span data-stu-id="6afff-157">Administrators can manage users who were previously moved from an on-premises Skype for Business Server to the cloud, even after the on-premises deployment is decommissioned.</span></span> <span data-ttu-id="6afff-158">Существует два варианта:</span><span class="sxs-lookup"><span data-stu-id="6afff-158">There are two different possibilities:</span></span>

- <span data-ttu-id="6afff-159">У пользователя не было значения для локальной организации lineURI перед перемещением.</span><span class="sxs-lookup"><span data-stu-id="6afff-159">The user did not have a value for lineURI on-premises before the move.</span></span> 

  <span data-ttu-id="6afff-160">В этом случае вы можете изменить LineURI с помощью параметров-Онпремлинеури в [командлете Set-CsUser](https://docs.microsoft.com/powershell/module/skype/set-csuser?view=skype-ps) в модуле PowerShell Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="6afff-160">In this case, you can modify the LineURI using the -onpremLineUri parameters in the [Set-Csuser cmdlet](https://docs.microsoft.com/powershell/module/skype/set-csuser?view=skype-ps) in the Skype for Business Online Powershell module.</span></span>

- <span data-ttu-id="6afff-161">Пользователь lineURI локально до перемещения (предположительно, так как пользователь включил поддержку корпоративной голосовой связи).</span><span class="sxs-lookup"><span data-stu-id="6afff-161">The user had a lineURI on-premises before the move (presumably because the user was enabled for Enterprise Voice).</span></span> 

  <span data-ttu-id="6afff-162">Если вы хотите изменить lineURI, это необходимо сделать в локальной службе Active Directory и приступать к Azure AD.</span><span class="sxs-lookup"><span data-stu-id="6afff-162">If you want to change the lineURI, you must do this in the on-premises Active Directory and let the value flow up to Azure AD.</span></span> <span data-ttu-id="6afff-163">Для этого не требуется локальная среда Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="6afff-163">This does NOT require on-premises Skype for Business Server.</span></span> <span data-ttu-id="6afff-164">Вместо этого этот атрибут, msRTCSIP, можно редактировать непосредственно в локальной службе Active Directory с помощью оснастки MMC "пользователи и компьютеры Active Directory" либо с помощью PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6afff-164">Rather, this attribute, msRTCSIP-Line, can be edited directly in the on-premises Active Directory, using either the Active Directory Users and Computers MMC snap-in, or by using PowerShell.</span></span> <span data-ttu-id="6afff-165">Если вы используете оснастку консоли управления (MMC), откройте страницу свойств пользователя, перейдите на вкладку Редактор атрибутов и найдите msRTCSIP-Line.</span><span class="sxs-lookup"><span data-stu-id="6afff-165">If you are using the MMC snap-in, open to the properties page of the user, click Attribute Editor tab, and find msRTCSIP-Line.</span></span>

  ![Средство "пользователи и компьютеры Active Directory"](../media/disable-hybrid-1.png)

## <a name="see-also"></a><span data-ttu-id="6afff-167">См. также</span><span class="sxs-lookup"><span data-stu-id="6afff-167">See also</span></span>

[<span data-ttu-id="6afff-168">Объединение в облако для Teams и Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="6afff-168">Cloud Consolidation for Teams and Skype for Business</span></span>](cloud-consolidation.md)
