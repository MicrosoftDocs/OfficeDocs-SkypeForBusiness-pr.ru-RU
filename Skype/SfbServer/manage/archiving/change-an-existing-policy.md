---
title: Изменение существующей политики архива в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 4cf600be-ba3d-4bce-aa22-e158b9ccf8a9
description: Сводка. Узнайте, как изменить политики архива пользователя для Skype для бизнеса Server.
ms.openlocfilehash: 47c9d5938c22b93db48c96265831cbf24ecc24d7
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817709"
---
# <a name="change-an-existing-archiving-policy-in-skype-for-business-server"></a><span data-ttu-id="064cc-103">Изменение существующей политики архива в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="064cc-103">Change an existing archiving policy in Skype for Business Server</span></span>
 
<span data-ttu-id="064cc-104">**Сводка:** Learn how to change user archiving policies for Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="064cc-104">**Summary:** Learn how to change user archiving policies for Skype for Business Server.</span></span>
  
<span data-ttu-id="064cc-105">При первом развертывании Skype для бизнеса Server необходимо настроить начальные политики архивации, определяющие реализации архивации для пользователей в развертывании.</span><span class="sxs-lookup"><span data-stu-id="064cc-105">When you first deploy Skype for Business Server, you set up initial archiving policies that determine how archiving is implemented for the users in your deployment.</span></span> <span data-ttu-id="064cc-106">В этом разделе описывается, как управлять политиками и изменять их.</span><span class="sxs-lookup"><span data-stu-id="064cc-106">This topic describes how to manage and amend policies.</span></span> 
  
## <a name="change-archiving-policies-by-using-the-control-panel"></a><span data-ttu-id="064cc-107">Изменение политик архива с помощью панели управления</span><span class="sxs-lookup"><span data-stu-id="064cc-107">Change archiving policies by using the Control Panel</span></span>

1. <span data-ttu-id="064cc-108">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsArchivingAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="064cc-108">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span> 
    
2. <span data-ttu-id="064cc-109">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="064cc-109">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="064cc-110">В левой панели навигации щелкните **"Мониторинг и** архивации" и выберите "Политика **архивации".**</span><span class="sxs-lookup"><span data-stu-id="064cc-110">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Policy**.</span></span>
    
4. <span data-ttu-id="064cc-111">В списке политик выполните одно из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="064cc-111">In the list of policies, do one of the following:</span></span> 
    
   - <span data-ttu-id="064cc-112">Чтобы изменить политику для всего развертывания, в списке политик щелкните **Global** (Глобальная), щелкните **Edit** (Изменить), а затем — **Show details** (Показать сведения).</span><span class="sxs-lookup"><span data-stu-id="064cc-112">To change the policy for your entire deployment, click **Global** in the list of policies, click **Edit**, and then click **Show details**.</span></span>
    
   - <span data-ttu-id="064cc-113">Чтобы изменить политику для одного сайта, выберите имя сайта в списке политик, щелкните **Edit** (Изменить) и затем щелкните **Show details** (Показать сведения).</span><span class="sxs-lookup"><span data-stu-id="064cc-113">To change the policy for a single site, click the site name in the list of policies, click **Edit**, and then click **Show details**.</span></span>
    
   - <span data-ttu-id="064cc-114">Чтобы изменить политику для отдельного пользователя или группы пользователей, выберите имя пользователя или группы пользователей в списке политик, щелкните **Edit** (Изменить) и затем щелкните **Show details** (Показать сведения).</span><span class="sxs-lookup"><span data-stu-id="064cc-114">To change the policy for a single user or user group, click the user or user group name in the list of policies, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="064cc-115">На странице **Edit Archiving Policy** (Изменение политики архивации) выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="064cc-115">On the **Edit Archiving Policy** page, do the following:</span></span>
    
   - <span data-ttu-id="064cc-116">Чтобы включить или отключить архивацию внутренних коммуникаций, установите или снимите флажок **Archive internal communications** (Архивировать внутренние коммуникации).</span><span class="sxs-lookup"><span data-stu-id="064cc-116">To enable or disable internal archiving for the policy, select or clear the **Archive internal communications** check box.</span></span>
    
   - <span data-ttu-id="064cc-117">Чтобы включить или отключить архивацию внешних коммуникаций, установите или снимите флажок **Archive external communications** (Архивировать внешние коммуникации).</span><span class="sxs-lookup"><span data-stu-id="064cc-117">To enable or disable external archiving for the policy, select or clear the **Archive external communications** check box.</span></span>
    
6. <span data-ttu-id="064cc-118">Щелкните **Commit** (Применить).</span><span class="sxs-lookup"><span data-stu-id="064cc-118">Click **Commit**.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="064cc-119">Параметры политики пользователя применяются только к тем пользователям и группам пользователей, к которым применяется политика.</span><span class="sxs-lookup"><span data-stu-id="064cc-119">The settings of a user policy only apply to the specific users and user groups to which you apply the policy.</span></span> <span data-ttu-id="064cc-120">Дополнительные сведения см. в сведениях о применении политики [архива к пользователям в Skype для бизнеса Server.](apply-a-policy-to-users.md)</span><span class="sxs-lookup"><span data-stu-id="064cc-120">For details, see [Apply an archiving policy to users in Skype for Business Server](apply-a-policy-to-users.md).</span></span> 
  
## <a name="change-archiving-policies-by-using-windows-powershell"></a><span data-ttu-id="064cc-121">Изменение политик архива с помощью Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="064cc-121">Change archiving policies by using Windows PowerShell</span></span>

<span data-ttu-id="064cc-122">Вы также можете изменить политики архива с помощью Windows PowerShell **Set-CsArchivingPolicy.**</span><span class="sxs-lookup"><span data-stu-id="064cc-122">You can also change archiving policies by using the Windows PowerShell **Set-CsArchivingPolicy** cmdlet.</span></span>
  
### <a name="enable-archiving-policies"></a><span data-ttu-id="064cc-123">Включить политики архива</span><span class="sxs-lookup"><span data-stu-id="064cc-123">Enable archiving policies</span></span>

<span data-ttu-id="064cc-124">Чтобы включить архивировать внутренние сеансы связи, установите для параметра ArchiveInternal значение True ($True):</span><span class="sxs-lookup"><span data-stu-id="064cc-124">To enable the archiving of internal communication sessions, set the value of the ArchiveInternal parameter to True ($True):</span></span> 
  
```PowerShell
Set-CsArchivingPolicy -Identity "global" -ArchiveInternal $True
```

<span data-ttu-id="064cc-125">Чтобы включить архивировать внешние сеансы связи, установите для параметра ArchiveExternal значение True ($True):</span><span class="sxs-lookup"><span data-stu-id="064cc-125">To enable the archiving of external communication sessions, set the value of the ArchiveExternal parameter to True ($True):</span></span> 
  
```PowerShell
Set-CsArchivingPolicy -Identity "global" -ArchiveExternal $True
```

<span data-ttu-id="064cc-126">Чтобы включить архивировать как внутренние, так и внешние сеансы связи, установите для параметров ArchiveInternal и ArchiveExternal значение True:</span><span class="sxs-lookup"><span data-stu-id="064cc-126">To enable the archiving of both internal and external communication sessions, set the value of both the ArchiveInternal and ArchiveExternal parameters to True:</span></span> 
  
```PowerShell
Set-CsArchivingPolicy -Identity "global" -ArchiveInternal $True -ArchiveExternal $True
```

### <a name="disable-archiving-policies"></a><span data-ttu-id="064cc-127">Отключение политик архива</span><span class="sxs-lookup"><span data-stu-id="064cc-127">Disable archiving policies</span></span>

<span data-ttu-id="064cc-128">Чтобы полностью отключить архивации, установите для параметров ArchiveInternal и ArchiveExternal значение False ($False):</span><span class="sxs-lookup"><span data-stu-id="064cc-128">To disable archiving altogether, set the value of both the ArchiveInternal and ArchiveExternal parameters to False ($False):</span></span> 
  
```PowerShell
Set-CsArchivingPolicy -Identity "global" -ArchiveInternal $False -ArchiveExternal $False
```
