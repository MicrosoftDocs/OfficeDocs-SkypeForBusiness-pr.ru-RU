---
title: Применение политики архивации для пользователей, Скайп для Business Server
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: bebd45d1-93c3-4e80-8933-755b699b2209
description: 'Сводка: Узнайте, как назначение политики архивации для пользователей, Скайп для Business Server.'
ms.openlocfilehash: bc54c25a710e4e1cca44fb7311a47101f31ef7df
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2018
ms.locfileid: "20985618"
---
# <a name="apply-an-archiving-policy-to-users-in-skype-for-business-server"></a><span data-ttu-id="0e533-103">Применение политики архивации для пользователей, Скайп для Business Server</span><span class="sxs-lookup"><span data-stu-id="0e533-103">Apply an archiving policy to users in Skype for Business Server</span></span>

<span data-ttu-id="0e533-104">**Сводка:** Узнайте, как назначение политики архивации для пользователей, Скайп для Business Server.</span><span class="sxs-lookup"><span data-stu-id="0e533-104">**Summary:** Learn how to assign an archiving policy to users in Skype for Business Server.</span></span>
  
<span data-ttu-id="0e533-105">Если вы создали одну или несколько политик пользователей для архивации для пользователей, размещенных на Скайп для Business Server, вы можете реализовать поддержки архивации для конкретных пользователей путем применения соответствующих политик для этих пользователей или групп пользователей.</span><span class="sxs-lookup"><span data-stu-id="0e533-105">If you have created one or more user policies for archiving for users homed on Skype for Business Server, you can implement archiving support for specific users by applying the appropriate policies to those users or user groups.</span></span> <span data-ttu-id="0e533-106">Например если создать политику для поддержки архивации внутренних коммуникаций, можно применить их хотя бы одному пользователю или группе пользователей для поддержки архивации из Скайп пользователя для коммуникаций Business Server.</span><span class="sxs-lookup"><span data-stu-id="0e533-106">For example, if you create a policy to support archiving of internal communications, you can apply it to at least one user or user group to support archiving of the user's Skype for Business Server communications.</span></span>
  
> [!NOTE]
> <span data-ttu-id="0e533-107">Если включена интеграция с Microsoft Exchange для вашего развертывания, управления политики хранения на месте Exchange ли архивации для пользователей, которые размещаются на сервере Exchange и установить их почтовые ящики на хранение на месте.</span><span class="sxs-lookup"><span data-stu-id="0e533-107">If you enabled Microsoft Exchange integration for your deployment, Exchange In-Place Hold policies control whether archiving is enabled for the users who are homed on Exchange and have their mailboxes put on In-Place Hold.</span></span> <span data-ttu-id="0e533-108">Дополнительные сведения см [Планирование архивации в Скайп для Business Server](../../plan-your-deployment/archiving/archiving.md) и [Настройка интеграции с хранилищем Exchange для Скайп для Business Server](../../deploy/deploy-archiving/configure-integration-with-exchange-storage.md).</span><span class="sxs-lookup"><span data-stu-id="0e533-108">For details, see [Plan for archiving in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md) and [Configure integration with Exchange storage for Skype for Business Server](../../deploy/deploy-archiving/configure-integration-with-exchange-storage.md).</span></span> 
  
## <a name="apply-a-user-policy-by-using-the-control-panel"></a><span data-ttu-id="0e533-109">Применение политики пользователей с помощью панели управления</span><span class="sxs-lookup"><span data-stu-id="0e533-109">Apply a user policy by using the Control Panel</span></span>

<span data-ttu-id="0e533-110">Чтобы применить политику пользователей с помощью панели управления, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="0e533-110">To apply a user policy by using the Control Panel:</span></span>
  
1. <span data-ttu-id="0e533-111">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsArchivingAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="0e533-111">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span> 
    
2. <span data-ttu-id="0e533-112">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть Скайп для панели управления Business Server.</span><span class="sxs-lookup"><span data-stu-id="0e533-112">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="0e533-113">На панели навигации слева нажмите **Пользователи** и затем найдите учетную запись пользователя, которую необходимо настроить.</span><span class="sxs-lookup"><span data-stu-id="0e533-113">In the left navigation bar, click **Users**, and then search for the user account that you want to configure.</span></span> 
    
4. <span data-ttu-id="0e533-114">В таблице с результатами поиска выберите нужную учетную запись, нажмите кнопку **Изменить** и выберите пункт **Показать сведения**.</span><span class="sxs-lookup"><span data-stu-id="0e533-114">In the table that lists the search results, click the user account, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="0e533-115">В **Окне Изменение пользователя Lync Server** в поле **Политика архивация**выберите политику, которую нужно применить.</span><span class="sxs-lookup"><span data-stu-id="0e533-115">In **Edit Lync Server User** under **Archiving policy**, select the archiving user policy that you want to apply.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="0e533-116">** \<Автоматического\> ** параметры применяются параметры установки сервера по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="0e533-116">The **\<Automatic\>** settings apply the default server installation settings.</span></span> <span data-ttu-id="0e533-117">Данные параметры автоматически применяются сервером.</span><span class="sxs-lookup"><span data-stu-id="0e533-117">These settings are applied automatically by the server.</span></span>
  
6. <span data-ttu-id="0e533-118">Нажмите **Исполнить**.</span><span class="sxs-lookup"><span data-stu-id="0e533-118">Click **Commit**.</span></span>
    
## <a name="apply-a-user-policy-by-using-windows-powershell"></a><span data-ttu-id="0e533-119">Применение пользовательской политики с помощью Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="0e533-119">Apply a user policy by using Windows PowerShell</span></span>

<span data-ttu-id="0e533-120">Также можно применить политику уровня пользователя с помощью командлета Windows PowerShell **Grant-CsArchivingPolicy** .</span><span class="sxs-lookup"><span data-stu-id="0e533-120">You can also apply a user policy by using the Windows PowerShell **Grant-CsArchivingPolicy** cmdlet.</span></span>
  
<span data-ttu-id="0e533-121">Следующей командой пользователю Ken Myer назначается политика архивации RedmondArchivingPolicy на уровне пользователей.</span><span class="sxs-lookup"><span data-stu-id="0e533-121">The following command assigns the per-user archiving policy RedmondArchivingPolicy to the user Ken Myer.</span></span>
  
```
Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName "RedmondArchivingPolicy"
```

<span data-ttu-id="0e533-122">Эта команда назначает политику архивации на уровне пользователя RedmondArchivingPolicy всем пользователям, чьи учетные записи размещены в пуле регистраторов atl-cs-001.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="0e533-122">This command assigns the per-user archiving policy RedmondArchivingPolicy to all users who have accounts homed on the Registrar pool atl-cs-001.contoso.com.</span></span> <span data-ttu-id="0e533-123">Для получения дополнительных сведений о параметр Filter, используемые в этой команде обратитесь к документации командлет [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="0e533-123">For details about the Filter parameter used in this command, see the [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps) cmdlet documentation.</span></span>
  
```
Get-CsUser -Filter {RegistrarPool -eq "atl-cs-001.contoso.com"} | Grant-CsArchivingPolicy -PolicyName "RedmondArchivingPolicy"
```

<span data-ttu-id="0e533-p105">Следующей командой удаляется любая политика архивации на уровне пользователей, ранее назначенная пользователю Ken Myer. После того как политика на уровне пользователей удалена, Ken Myer будет автоматически управляться с помощью глобальной политики или политики его локального сайта, если такая существует. Политика сайта имеет приоритет над глобальной политикой.</span><span class="sxs-lookup"><span data-stu-id="0e533-p105">The following command removes any per-user archiving policy previously assigned to Ken Myer. After the per-user policy is removed, Ken Myer will automatically be managed by using the global policy or, if one exists, his local site policy. A site policy takes precedence over the global policy.</span></span>
  
```
Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName $Null
```

<span data-ttu-id="0e533-127">Для получения дополнительных сведений обратитесь к документации командлета [Grant-CsArchivingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csarchivingpolicy?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="0e533-127">For details, see the [Grant-CsArchivingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csarchivingpolicy?view=skype-ps) cmdlet documentation.</span></span>
  

