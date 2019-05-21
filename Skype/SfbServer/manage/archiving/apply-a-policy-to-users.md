---
title: Применение к пользователям политики архивации в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: bebd45d1-93c3-4e80-8933-755b699b2209
description: 'Сводка: сведения о назначении политики архивации пользователям в Skype для бизнеса Server.'
ms.openlocfilehash: 895a7fac34fcac0a4a7e39756796f6b7d2fc6377
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34282051"
---
# <a name="apply-an-archiving-policy-to-users-in-skype-for-business-server"></a><span data-ttu-id="2e32d-103">Применение к пользователям политики архивации в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="2e32d-103">Apply an archiving policy to users in Skype for Business Server</span></span>

<span data-ttu-id="2e32d-104">**Сводка:** Сведения о назначении пользователям политики архивации в Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="2e32d-104">**Summary:** Learn how to assign an archiving policy to users in Skype for Business Server.</span></span>
  
<span data-ttu-id="2e32d-105">Если вы создали одну или несколько политик пользователей для архивации для пользователей, размещенных на сервере Skype для бизнеса Server, вы можете реализовать поддержку архивации для определенных пользователей, применяя соответствующие политики к этим пользователям или группам пользователей.</span><span class="sxs-lookup"><span data-stu-id="2e32d-105">If you have created one or more user policies for archiving for users homed on Skype for Business Server, you can implement archiving support for specific users by applying the appropriate policies to those users or user groups.</span></span> <span data-ttu-id="2e32d-106">Например, если вы создаете политику для поддержки архивации внутренних данных, вы можете применить ее по крайней мере к одному пользователю или группе пользователей для поддержки архивации данных пользователя в Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="2e32d-106">For example, if you create a policy to support archiving of internal communications, you can apply it to at least one user or user group to support archiving of the user's Skype for Business Server communications.</span></span>
  
> [!NOTE]
> <span data-ttu-id="2e32d-107">Если вы включили интеграцию Microsoft Exchange для развертывания, политики хранения на месте Exchange определяют, разрешено ли архивирование для пользователей, использующих Exchange, и почтовые ящики, которые помещаются на хранение на месте.</span><span class="sxs-lookup"><span data-stu-id="2e32d-107">If you enabled Microsoft Exchange integration for your deployment, Exchange In-Place Hold policies control whether archiving is enabled for the users who are homed on Exchange and have their mailboxes put on In-Place Hold.</span></span> <span data-ttu-id="2e32d-108">Подробности можно найти [в разделе Планирование архивации в Skype для бизнеса Server](../../plan-your-deployment/archiving/archiving.md) и [Настройка интеграции с хранилищем Exchange для Skype для бизнеса Server](../../deploy/deploy-archiving/configure-integration-with-exchange-storage.md).</span><span class="sxs-lookup"><span data-stu-id="2e32d-108">For details, see [Plan for archiving in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md) and [Configure integration with Exchange storage for Skype for Business Server](../../deploy/deploy-archiving/configure-integration-with-exchange-storage.md).</span></span> 
  
## <a name="apply-a-user-policy-by-using-the-control-panel"></a><span data-ttu-id="2e32d-109">Применение политики пользователей с помощью панели управления</span><span class="sxs-lookup"><span data-stu-id="2e32d-109">Apply a user policy by using the Control Panel</span></span>

<span data-ttu-id="2e32d-110">Чтобы применить политику пользователей с помощью панели управления, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="2e32d-110">To apply a user policy by using the Control Panel:</span></span>
  
1. <span data-ttu-id="2e32d-111">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsArchivingAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="2e32d-111">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span> 
    
2. <span data-ttu-id="2e32d-112">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="2e32d-112">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="2e32d-113">На панели навигации слева нажмите **Пользователи** и затем найдите учетную запись пользователя, которую необходимо настроить.</span><span class="sxs-lookup"><span data-stu-id="2e32d-113">In the left navigation bar, click **Users**, and then search for the user account that you want to configure.</span></span> 
    
4. <span data-ttu-id="2e32d-114">В таблице с результатами поиска выберите нужную учетную запись, нажмите кнопку **Изменить** и выберите пункт **Показать сведения**.</span><span class="sxs-lookup"><span data-stu-id="2e32d-114">In the table that lists the search results, click the user account, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="2e32d-115">В диалоговом окне **изменение пользователя Lync Server** в разделе **Политика архивации**выберите политику архивации пользователей, которую вы хотите применить.</span><span class="sxs-lookup"><span data-stu-id="2e32d-115">In **Edit Lync Server User** under **Archiving policy**, select the archiving user policy that you want to apply.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="2e32d-116">Для \*\* \<параметров\> автоматической\*\* настройки применяются параметры установки сервера по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="2e32d-116">The **\<Automatic\>** settings apply the default server installation settings.</span></span> <span data-ttu-id="2e32d-117">Данные параметры автоматически применяются сервером.</span><span class="sxs-lookup"><span data-stu-id="2e32d-117">These settings are applied automatically by the server.</span></span>
  
6. <span data-ttu-id="2e32d-118">Нажмите **Исполнить**.</span><span class="sxs-lookup"><span data-stu-id="2e32d-118">Click **Commit**.</span></span>
    
## <a name="apply-a-user-policy-by-using-windows-powershell"></a><span data-ttu-id="2e32d-119">Применение политики пользователей с помощью Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="2e32d-119">Apply a user policy by using Windows PowerShell</span></span>

<span data-ttu-id="2e32d-120">Вы также можете применить политику пользователей с помощью командлета **Grant-Ксарчивингполици** Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2e32d-120">You can also apply a user policy by using the Windows PowerShell **Grant-CsArchivingPolicy** cmdlet.</span></span>
  
<span data-ttu-id="2e32d-121">Следующей командой пользователю Ken Myer назначается политика архивации RedmondArchivingPolicy на уровне пользователей.</span><span class="sxs-lookup"><span data-stu-id="2e32d-121">The following command assigns the per-user archiving policy RedmondArchivingPolicy to the user Ken Myer.</span></span>
  
```
Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName "RedmondArchivingPolicy"
```

<span data-ttu-id="2e32d-122">Эта команда назначает политику архивации на уровне пользователя RedmondArchivingPolicy всем пользователям, чьи учетные записи размещены в пуле регистраторов atl-cs-001.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="2e32d-122">This command assigns the per-user archiving policy RedmondArchivingPolicy to all users who have accounts homed on the Registrar pool atl-cs-001.contoso.com.</span></span> <span data-ttu-id="2e32d-123">Дополнительные сведения о параметре фильтрации, используемом в этой команде, можно найти в документации по командлету [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="2e32d-123">For details about the Filter parameter used in this command, see the [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps) cmdlet documentation.</span></span>
  
```
Get-CsUser -Filter {RegistrarPool -eq "atl-cs-001.contoso.com"} | Grant-CsArchivingPolicy -PolicyName "RedmondArchivingPolicy"
```

<span data-ttu-id="2e32d-p105">Следующей командой удаляется любая политика архивации на уровне пользователей, ранее назначенная пользователю Ken Myer. После того как политика на уровне пользователей удалена, Ken Myer будет автоматически управляться с помощью глобальной политики или политики его локального сайта, если такая существует. Политика сайта имеет приоритет над глобальной политикой.</span><span class="sxs-lookup"><span data-stu-id="2e32d-p105">The following command removes any per-user archiving policy previously assigned to Ken Myer. After the per-user policy is removed, Ken Myer will automatically be managed by using the global policy or, if one exists, his local site policy. A site policy takes precedence over the global policy.</span></span>
  
```
Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName $Null
```

<span data-ttu-id="2e32d-127">Дополнительные сведения можно найти в документации по командлету [Grant-ксарчивингполици](https://docs.microsoft.com/powershell/module/skype/grant-csarchivingpolicy?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="2e32d-127">For details, see the [Grant-CsArchivingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csarchivingpolicy?view=skype-ps) cmdlet documentation.</span></span>
  

