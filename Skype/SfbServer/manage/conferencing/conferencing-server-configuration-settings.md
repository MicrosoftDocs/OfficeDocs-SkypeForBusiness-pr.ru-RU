---
title: Управление настройками конфигурации сервераконференций в Skype для бизнеса Server
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
ms.assetid: 36bed690-6e22-4e11-88c1-b40a20836c6a
description: Сводка. Узнайте, как управлять настройками конфигурации сервера конфигурации сервераконференций в Skype для бизнеса Server.
ms.openlocfilehash: 7f8714a4098285e955b559b2baf70d74957159a1
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49828289"
---
# <a name="manage-conferencing-server-configuration-settings-in-skype-for-business-server"></a><span data-ttu-id="1bcd6-103">Управление настройками конфигурации сервераконференций в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="1bcd6-103">Manage conferencing server configuration settings in Skype for Business Server</span></span>
 
<span data-ttu-id="1bcd6-104">**Сводка:** Learn how to manage conferencing server configuration settings in Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="1bcd6-104">**Summary:** Learn how to manage conferencing server configuration settings in Skype for Business Server.</span></span>
  
<span data-ttu-id="1bcd6-105">В этом разделе описывается, как управлять настройками конфигурации для conferencing.</span><span class="sxs-lookup"><span data-stu-id="1bcd6-105">This topic describes how to manage conferencing configuration settings.</span></span> <span data-ttu-id="1bcd6-106">Дополнительные сведения о планировании и развертывании [conferencing](../../plan-your-deployment/conferencing/conferencing.md) см. в дополнительных сведениях о планировании и развертывании в Skype для бизнеса [Server.](../../deploy/deploy-conferencing/deploy-conferencing.md)</span><span class="sxs-lookup"><span data-stu-id="1bcd6-106">For more information about how to plan and deploy conferencing, see [Plan for conferencing in Skype for Business Server](../../plan-your-deployment/conferencing/conferencing.md) and [Deploy conferencing in Skype for Business Server](../../deploy/deploy-conferencing/deploy-conferencing.md).</span></span>
  
<span data-ttu-id="1bcd6-107">Параметры конфигурации проведения собраний определяют такие параметры, как максимальный допустимый размер содержимого собрания и раздаточной информации; максимальная пропускная способность для службы общего доступа к приложениям; ограничения хранилища и сроки действия; URL-адреса для внутренних и внешних загрузок поддерживаемого клиента; указатели на внутренние и внешние URL-адреса, в которых пользователи могут получить справку и ресурсы по видеоконференциям; порты, используемые для общего доступа к приложениям, клиентского звука, передачи файлов и трафика мультимедиа;</span><span class="sxs-lookup"><span data-stu-id="1bcd6-107">Conferencing configuration settings determine such things as the maximum allowed size for meeting content and handouts; maximum amount of bandwidth for the Application Sharing Conferencing service; storage limits and expiration periods; the URLs for the internal and external downloads of the supported client; pointers to internal and external URLs where users can obtain conferencing help and resources; and the ports used for application sharing, client audio, file transfers, and media traffic.</span></span> <span data-ttu-id="1bcd6-108">Эти параметры позволяют управлять фактическими серверами самостоятельно.</span><span class="sxs-lookup"><span data-stu-id="1bcd6-108">These settings allow you to manage the actual servers themselves.</span></span> <span data-ttu-id="1bcd6-109">Эти параметры можно настроить с помощью оболочки управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="1bcd6-109">These settings can be set by using Skype for Business Server Management Shell.</span></span>
  
<span data-ttu-id="1bcd6-110">При установке Skype для бизнеса Server система предоставляет одну коллекцию параметров конфигурации (глобальной коллекции).</span><span class="sxs-lookup"><span data-stu-id="1bcd6-110">When you install Skype for Business Server, the system provides you with a single collection of conferencing configuration settings (the global collection).</span></span> <span data-ttu-id="1bcd6-111">Если необходимо создать настраиваемые параметры для сайта или службы, это можно сделать с помощью cmdlet **New-CsConferencingConfiguration.**</span><span class="sxs-lookup"><span data-stu-id="1bcd6-111">If you need to create custom settings for a site or service, you can do so using the **New-CsConferencingConfiguration** cmdlet.</span></span> <span data-ttu-id="1bcd6-112">Обратите внимание, что новые параметры можно применять только на уровне сайта или службы; Невозможно создать глобальную коллекцию параметров конфигурации, но глобальную коллекцию можно изменить с помощью **cmdlet Set-CsConferencingConfiguration.**</span><span class="sxs-lookup"><span data-stu-id="1bcd6-112">Note that new settings can be applied only at the site or service scope; you cannot create a new global collection of conferencing configuration settings, but you can modify the global collection by using the **Set-CsConferencingConfiguration** cmdlet.</span></span> <span data-ttu-id="1bcd6-113">Кроме того, ни на одном сайте или в службе не может быть более одной коллекции параметров.</span><span class="sxs-lookup"><span data-stu-id="1bcd6-113">In addition, no site or service can host more than one collection of settings.</span></span> <span data-ttu-id="1bcd6-114">Если попытаться создать новые параметры для сайта Redmond, а на сайте Redmond уже размещена коллекция параметров конфигурации, команда не будет работать.</span><span class="sxs-lookup"><span data-stu-id="1bcd6-114">If you try to create new settings for the Redmond site and the Redmond site already hosts a collection of conferencing configuration settings, then your command will fail.</span></span>
  
## <a name="manage-conferencing-configuration-settings-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="1bcd6-115">Manage conferencing configuration settings by using Skype for Business Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="1bcd6-115">Manage conferencing configuration settings by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="1bcd6-116">Для управления настройками конфигурации с помощью skype для бизнеса Server Management Shell используйте следующие команды:</span><span class="sxs-lookup"><span data-stu-id="1bcd6-116">To manage conferencing configuration settings by using Skype for Business Server Management Shell, use the following cmdlets:</span></span>
  
<span data-ttu-id="1bcd6-117">**Параметры конфигурации conferencing**</span><span class="sxs-lookup"><span data-stu-id="1bcd6-117">**Conferencing configuration settings**</span></span>

|<span data-ttu-id="1bcd6-118">**Командлет**</span><span class="sxs-lookup"><span data-stu-id="1bcd6-118">**Cmdlet**</span></span>|<span data-ttu-id="1bcd6-119">**Описание**</span><span class="sxs-lookup"><span data-stu-id="1bcd6-119">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="1bcd6-120">Get-CsConferencingConfiguration</span><span class="sxs-lookup"><span data-stu-id="1bcd6-120">Get-CsConferencingConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csconferencingconfiguration?view=skype-ps) <br/> |<span data-ttu-id="1bcd6-121">Возвращает сведения о параметрах конфигурации для организации.</span><span class="sxs-lookup"><span data-stu-id="1bcd6-121">Returns information about the conferencing configuration settings for your organization.</span></span>  <br/> |
|[<span data-ttu-id="1bcd6-122">New-CsConferencingConfiguration</span><span class="sxs-lookup"><span data-stu-id="1bcd6-122">New-CsConferencingConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csconferencingconfiguration?view=skype-ps) <br/> |<span data-ttu-id="1bcd6-123">Создает новую коллекцию параметров конфигурации для собраний.</span><span class="sxs-lookup"><span data-stu-id="1bcd6-123">Creates a new collection of conferencing configuration settings.</span></span>  <br/> |
|[<span data-ttu-id="1bcd6-124">Remove-CsConferencingConfiguration</span><span class="sxs-lookup"><span data-stu-id="1bcd6-124">Remove-CsConferencingConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-csconferencingconfiguration?view=skype-ps) <br/> |<span data-ttu-id="1bcd6-125">Удаляет указанную коллекцию параметров конфигурации conferencing.</span><span class="sxs-lookup"><span data-stu-id="1bcd6-125">Removes the specified collection of conferencing configuration settings.</span></span>  <br/> |
|[<span data-ttu-id="1bcd6-126">Set-CsConferencingConfiguration</span><span class="sxs-lookup"><span data-stu-id="1bcd6-126">Set-CsConferencingConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csconferencingconfiguration?view=skype-ps) <br/> |<span data-ttu-id="1bcd6-127">Изменяет существующую коллекцию параметров конфигурации конференц-связи.</span><span class="sxs-lookup"><span data-stu-id="1bcd6-127">Modifies an existing collection of conferencing configuration settings.</span></span>  <br/> |
   
<span data-ttu-id="1bcd6-128">Следующая команда создает новую коллекцию параметров конфигурации для сайта Redmond (site:Redmond).</span><span class="sxs-lookup"><span data-stu-id="1bcd6-128">The following command creates a new collection of conferencing configuration settings for the Redmond site (site:Redmond).</span></span> <span data-ttu-id="1bcd6-129">В этом примере включается один дополнительный параметр (Organization), который используется для того, чтобы установить для свойства Organization значение Litwareinc:</span><span class="sxs-lookup"><span data-stu-id="1bcd6-129">In this example, one additional parameter is included (Organization) which is used to set the value of the Organization property to Litwareinc:</span></span> 
  
```PowerShell
New-CsConferencingConfiguration -Identity site:Redmond -Organization Litwareinc
```

<span data-ttu-id="1bcd6-130">Обратите внимание, что на сайте может быть только одна такая коллекция, поэтому эта команда не удастся, если на сайте Redmond уже есть коллекция параметров конфигурации для собраний.</span><span class="sxs-lookup"><span data-stu-id="1bcd6-130">Note that you can have only one such collection per site, so this command would fail if the Redmond site already has a collection of conferencing configuration settings.</span></span> 
  
<span data-ttu-id="1bcd6-131">В следующем примере определяется новая коллекция параметров конфигурации, которые изначально хранятся в памяти, а затем применяются к сайту Redmond позже.</span><span class="sxs-lookup"><span data-stu-id="1bcd6-131">The next example defines a new collection of conferencing configuration settings, which are stored in memory initially, and then applied to the Redmond site at a later time.</span></span> 
  
<span data-ttu-id="1bcd6-132">Первая команда использует командлет **New-CsConferencingConfiguration** для создания новой коллекции параметров в памяти, хранимых в переменной $x.</span><span class="sxs-lookup"><span data-stu-id="1bcd6-132">The first command uses the **New-CsConferencingConfiguration** cmdlet to create a new, in-memory collection of settings stored in the variable $x.</span></span> <span data-ttu-id="1bcd6-133">Параметр InMemory указывает, что коллекция должна создаваться в памяти, а не сразу применяться к сайту Redmond.</span><span class="sxs-lookup"><span data-stu-id="1bcd6-133">The InMemory parameter specifies that the collection should be created in memory rather than immediately applied to the Redmond site.</span></span>
  
<span data-ttu-id="1bcd6-134">После создания коллекции вторая команда присваивает свойству Organization значение Litwareinc.</span><span class="sxs-lookup"><span data-stu-id="1bcd6-134">After the collection has been created, the second command sets the value of the Organization property to Litwareinc.</span></span> 
  
<span data-ttu-id="1bcd6-135">Наконец, третья команда использует командлет **Set-CsConferencingConfiguration** для применения новых параметров к сайту Redmond:</span><span class="sxs-lookup"><span data-stu-id="1bcd6-135">Finally, the third command uses the **Set-CsConferencingConfiguration** cmdlet to actually apply the new settings to the Redmond site:</span></span>
  
```PowerShell
$x = New-CsConferencingConfiguration -Identity site:Redmond -InMemory
$x.Organization = "Litwareinc"
Set-CsConferencingConfiguration -Instance $x
```

<span data-ttu-id="1bcd6-136">Если не вызвать cmdlet **Set-CsConferencingConfiguration,** новые параметры никогда не будут действовать.</span><span class="sxs-lookup"><span data-stu-id="1bcd6-136">If you do not call the **Set-CsConferencingConfiguration** cmdlet, the new settings will never take effect.</span></span> <span data-ttu-id="1bcd6-137">Вместо этого они исчезнут, как только вы завершите сеанс Windows PowerShell или удалите переменную $x.</span><span class="sxs-lookup"><span data-stu-id="1bcd6-137">Instead, they will disappear as soon as you end your Windows PowerShell session or delete the variable $x.</span></span>
  

