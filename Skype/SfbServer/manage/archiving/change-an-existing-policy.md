---
title: Изменение существующей политики архивации в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 4cf600be-ba3d-4bce-aa22-e158b9ccf8a9
description: 'Сводка: сведения о том, как изменить политики архивации пользователей в Skype для бизнеса Server.'
ms.openlocfilehash: 010365b5805517db8f40aa7e3e839fdb15115c06
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818991"
---
# <a name="change-an-existing-archiving-policy-in-skype-for-business-server"></a><span data-ttu-id="e5bee-103">Изменение существующей политики архивации в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="e5bee-103">Change an existing archiving policy in Skype for Business Server</span></span>
 
<span data-ttu-id="e5bee-104">**Сводка:** Сведения о том, как изменить политики архивации пользователей в Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="e5bee-104">**Summary:** Learn how to change user archiving policies for Skype for Business Server.</span></span>
  
<span data-ttu-id="e5bee-105">При первом развертывании сервера Skype для бизнеса вы настраиваете начальные политики архивации, определяющие способ реализации архивации для пользователей в вашем развертывании.</span><span class="sxs-lookup"><span data-stu-id="e5bee-105">When you first deploy Skype for Business Server, you set up initial archiving policies that determine how archiving is implemented for the users in your deployment.</span></span> <span data-ttu-id="e5bee-106">В этом разделе описываются способы управления политиками и их изменения.</span><span class="sxs-lookup"><span data-stu-id="e5bee-106">This topic describes how to manage and amend policies.</span></span> 
  
## <a name="change-archiving-policies-by-using-the-control-panel"></a><span data-ttu-id="e5bee-107">Изменение политик архивации с помощью панели управления</span><span class="sxs-lookup"><span data-stu-id="e5bee-107">Change archiving policies by using the Control Panel</span></span>

1. <span data-ttu-id="e5bee-108">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsArchivingAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="e5bee-108">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span> 
    
2. <span data-ttu-id="e5bee-109">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="e5bee-109">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="e5bee-110">На левой панели навигации щелкните **Мониторинг и архивация**, а затем щелкните **Политика архивации**.</span><span class="sxs-lookup"><span data-stu-id="e5bee-110">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Policy**.</span></span>
    
4. <span data-ttu-id="e5bee-111">В списке политик выполните одно из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="e5bee-111">In the list of policies, do one of the following:</span></span> 
    
   - <span data-ttu-id="e5bee-112">Чтобы изменить политику для всего развертывания, в списке политик щелкните **Global** (Глобальная), щелкните **Edit** (Изменить), а затем — **Show details** (Показать сведения).</span><span class="sxs-lookup"><span data-stu-id="e5bee-112">To change the policy for your entire deployment, click **Global** in the list of policies, click **Edit**, and then click **Show details**.</span></span>
    
   - <span data-ttu-id="e5bee-113">Чтобы изменить политику для одного сайта, выберите имя сайта в списке политик, щелкните **Edit** (Изменить) и затем щелкните **Show details** (Показать сведения).</span><span class="sxs-lookup"><span data-stu-id="e5bee-113">To change the policy for a single site, click the site name in the list of policies, click **Edit**, and then click **Show details**.</span></span>
    
   - <span data-ttu-id="e5bee-114">Чтобы изменить политику для отдельного пользователя или группы пользователей, выберите имя пользователя или группы пользователей в списке политик, щелкните **Edit** (Изменить) и затем щелкните **Show details** (Показать сведения).</span><span class="sxs-lookup"><span data-stu-id="e5bee-114">To change the policy for a single user or user group, click the user or user group name in the list of policies, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="e5bee-115">На странице **Edit Archiving Policy** (Изменение политики архивации) выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="e5bee-115">On the **Edit Archiving Policy** page, do the following:</span></span>
    
   - <span data-ttu-id="e5bee-116">Чтобы включить или отключить архивацию внутренних коммуникаций, установите или снимите флажок **Archive internal communications** (Архивировать внутренние коммуникации).</span><span class="sxs-lookup"><span data-stu-id="e5bee-116">To enable or disable internal archiving for the policy, select or clear the **Archive internal communications** check box.</span></span>
    
   - <span data-ttu-id="e5bee-117">Чтобы включить или отключить архивацию внешних коммуникаций, установите или снимите флажок **Archive external communications** (Архивировать внешние коммуникации).</span><span class="sxs-lookup"><span data-stu-id="e5bee-117">To enable or disable external archiving for the policy, select or clear the **Archive external communications** check box.</span></span>
    
6. <span data-ttu-id="e5bee-118">Нажмите **Исполнить**.</span><span class="sxs-lookup"><span data-stu-id="e5bee-118">Click **Commit**.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="e5bee-119">Параметры политики пользователя применяются только к тем пользователям и группам пользователей, к которым применяется политика.</span><span class="sxs-lookup"><span data-stu-id="e5bee-119">The settings of a user policy only apply to the specific users and user groups to which you apply the policy.</span></span> <span data-ttu-id="e5bee-120">Подробнее смотрите в разделе [применение политики архивации для пользователей в Skype для бизнеса Server](apply-a-policy-to-users.md).</span><span class="sxs-lookup"><span data-stu-id="e5bee-120">For details, see [Apply an archiving policy to users in Skype for Business Server](apply-a-policy-to-users.md).</span></span> 
  
## <a name="change-archiving-policies-by-using-windows-powershell"></a><span data-ttu-id="e5bee-121">Изменение политик архивации с помощью Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="e5bee-121">Change archiving policies by using Windows PowerShell</span></span>

<span data-ttu-id="e5bee-122">Политики архивации можно изменить, используя командлет Windows PowerShell **Set-CsArchivingPolicy**.</span><span class="sxs-lookup"><span data-stu-id="e5bee-122">You can also change archiving policies by using the Windows PowerShell **Set-CsArchivingPolicy** cmdlet.</span></span>
  
### <a name="enable-archiving-policies"></a><span data-ttu-id="e5bee-123">Включение политик архивации</span><span class="sxs-lookup"><span data-stu-id="e5bee-123">Enable archiving policies</span></span>

<span data-ttu-id="e5bee-124">Чтобы включить архивацию внутренних сеансов связи, присвойте параметру ArchiveInternal значение True ($True):</span><span class="sxs-lookup"><span data-stu-id="e5bee-124">To enable the archiving of internal communication sessions, set the value of the ArchiveInternal parameter to True ($True):</span></span> 
  
```PowerShell
Set-CsArchivingPolicy -Identity "global" -ArchiveInternal $True
```

<span data-ttu-id="e5bee-125">Чтобы включить архивацию внешних сеансов связи, присвойте параметру ArchiveExternal значение True ($True):</span><span class="sxs-lookup"><span data-stu-id="e5bee-125">To enable the archiving of external communication sessions, set the value of the ArchiveExternal parameter to True ($True):</span></span> 
  
```PowerShell
Set-CsArchivingPolicy -Identity "global" -ArchiveExternal $True
```

<span data-ttu-id="e5bee-126">Чтобы включить архивацию внутренних и внешних сеансов связи, установите для параметров Арчивеинтернал и Арчивикстернал значение true:</span><span class="sxs-lookup"><span data-stu-id="e5bee-126">To enable the archiving of both internal and external communication sessions, set the value of both the ArchiveInternal and ArchiveExternal parameters to True:</span></span> 
  
```PowerShell
Set-CsArchivingPolicy -Identity "global" -ArchiveInternal $True -ArchiveExternal $True
```

### <a name="disable-archiving-policies"></a><span data-ttu-id="e5bee-127">Отключение политик архивации</span><span class="sxs-lookup"><span data-stu-id="e5bee-127">Disable archiving policies</span></span>

<span data-ttu-id="e5bee-128">Чтобы полностью отключить архивацию, присвойте параметрам ArchiveInternal и ArchiveExternal значение False ($False):</span><span class="sxs-lookup"><span data-stu-id="e5bee-128">To disable archiving altogether, set the value of both the ArchiveInternal and ArchiveExternal parameters to False ($False):</span></span> 
  
```PowerShell
Set-CsArchivingPolicy -Identity "global" -ArchiveInternal $False -ArchiveExternal $False
```
