---
title: Настройка записи сведений о звонке и параметров качества обслуживания в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 009a0499-4f8c-450d-9c72-a565a08e9f7a
description: 'Сводка: сведения о настройке CDR и QoE в Skype для бизнеса Server.'
ms.openlocfilehash: 8a83e5920de60d664e76590d2b5b2a9f36b589ae
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34306642"
---
# <a name="configure-call-detail-recording-and-quality-of-experience-settings-in-skype-for-business-server"></a><span data-ttu-id="5d67f-103">Настройка записи сведений о звонке и параметров качества обслуживания в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="5d67f-103">Configure call detail recording and Quality of Experience settings in Skype for Business Server</span></span>
 
<span data-ttu-id="5d67f-104">**Сводка:** Научитесь настраивать CDR и QoE в Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="5d67f-104">**Summary:** Learn how to configure CDR and QoE in Skype for Business Server.</span></span>
  
<span data-ttu-id="5d67f-105">Настройка мониторинга CDR и QoE с помощью отчетов служб SQL Server Reporting Services для Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="5d67f-105">Configure CDR and QoE monitoring using SQL Server Reporting Services reports for Skype for Business Server.</span></span>
  
## <a name="configure-cdr-and-qoe"></a><span data-ttu-id="5d67f-106">Настройка CDR и качества взаимодействия</span><span class="sxs-lookup"><span data-stu-id="5d67f-106">Configure CDR and QoE</span></span>

<span data-ttu-id="5d67f-107">После связывания хранилища мониторинга с пулом переднего плана Настройте хранилище мониторинга, а затем установите и настройте службы отчетов SQL Server и Отслеживайте отчеты, которые можно управлять записью сведений о вызове (CDR) и качеством (QoE). наблюдение с помощью командной консоли Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="5d67f-107">After you have associated a monitoring store with a Front End pool, set up the monitoring store, and then installed and configured SQL Server Reporting Services and Monitoring Reports you can manage Call Detail Recording (CDR) and Quality of Experience (QoE) monitoring by using Skype for Business Server Management Shell.</span></span> <span data-ttu-id="5d67f-108">Командлеты командной консоли Skype для бизнеса Server позволяют включать и отключать CDR и/или QoE мониторинг для определенного сайта или для всего развертывания Skype для бизнеса Server. Это можно сделать с помощью команды.</span><span class="sxs-lookup"><span data-stu-id="5d67f-108">Skype for Business Server Management Shell cmdlets allow you to enable and disable CDR and/or QoE monitoring for a particular site or for your entire Skype for Business Server deployment; that can be done with a command as simple as this:</span></span>
  
```
Set-CsQoEConfiguration -Identity "global" -EnableQoE $False
```

<span data-ttu-id="5d67f-109">При установке Skype для бизнеса Server вы также устанавливаете предопределенную коллекцию глобальных параметров конфигурации для CDR и QoE.</span><span class="sxs-lookup"><span data-stu-id="5d67f-109">When you install Skype for Business Server, you will also install a predefined collection of global configuration settings for both CDR and QoE.</span></span> <span data-ttu-id="5d67f-110">В следующей таблице приведены значения по умолчанию для некоторых из наиболее часто используемых CDR параметров.</span><span class="sxs-lookup"><span data-stu-id="5d67f-110">Default values for some of the more commonly-used settings used by Call Detail Recording are shown in the following table:</span></span>
  
|<span data-ttu-id="5d67f-111">**Свойство**</span><span class="sxs-lookup"><span data-stu-id="5d67f-111">**Property**</span></span>|<span data-ttu-id="5d67f-112">**Описание**</span><span class="sxs-lookup"><span data-stu-id="5d67f-112">**Description**</span></span>|<span data-ttu-id="5d67f-113">**Значение по умолчанию**</span><span class="sxs-lookup"><span data-stu-id="5d67f-113">**Default Value**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="5d67f-114">EnableCDR</span><span class="sxs-lookup"><span data-stu-id="5d67f-114">EnableCDR</span></span>  <br/> |<span data-ttu-id="5d67f-p103">Указывает, включен ли мониторинг регистрации вызовов (CDR). Если установлено значение True, то все записи CDR будут собираться и записываться в базу данных мониторинга.</span><span class="sxs-lookup"><span data-stu-id="5d67f-p103">Indicates whether or not CDR is enabled. If True, all CDR records will be collected and written to the monitoring database.</span></span>  <br/> |<span data-ttu-id="5d67f-117">True</span><span class="sxs-lookup"><span data-stu-id="5d67f-117">True</span></span>  <br/> |
|<span data-ttu-id="5d67f-118">EnablePurging</span><span class="sxs-lookup"><span data-stu-id="5d67f-118">EnablePurging</span></span>  <br/> |<span data-ttu-id="5d67f-p104">Указывает, будут ли записи CDR периодически удаляться из базы данных. Если установлено значение True, то записи будут удаляться после периода времени, заданного в свойствах KeepCallDetailForDays (для записей CDR) и KeepErrorReportForDays (для ошибок CDR). Если параметр имеет значение False, то записи CDR будут сохраняться неопределенное время.</span><span class="sxs-lookup"><span data-stu-id="5d67f-p104">Indicates whether or not CDR records will periodically be deleted from the database. If True, records will be deleted after the time period specified by the properties KeepCallDetailForDays (for CDR records) and KeepErrorReportForDays (for CDR errors). If False, CDR records will be maintained indefinitely.</span></span>  <br/> |<span data-ttu-id="5d67f-122">True</span><span class="sxs-lookup"><span data-stu-id="5d67f-122">True</span></span>  <br/> |
|<span data-ttu-id="5d67f-123">KeepCallDetailForDays</span><span class="sxs-lookup"><span data-stu-id="5d67f-123">KeepCallDetailForDays</span></span>  <br/> |<span data-ttu-id="5d67f-p105">Задает период в днях, в течение которого записи CDR будут сохраняться в базе данных; все записи старше заданного количества дней будут автоматически удаляться. Однако это будет происходить только в том случае, если включена очистка.</span><span class="sxs-lookup"><span data-stu-id="5d67f-p105">Indicates the number of days that CDR records will be kept in the database; any records older than the specified number of days will automatically be deleted. However, this will occur only if purging has been enabled.</span></span>  <br/> <span data-ttu-id="5d67f-126">В качестве значения параметра KeepCallDetailForDays может быть установлено любое целое число от 1 до 2562 дней (приблизительно 7 лет).</span><span class="sxs-lookup"><span data-stu-id="5d67f-126">KeepCallDetailForDays can be set to any integer value between 1 and 2562 days (approximately 7 years).</span></span>  <br/> |<span data-ttu-id="5d67f-127">60 дней</span><span class="sxs-lookup"><span data-stu-id="5d67f-127">60 days</span></span>  <br/> |
|<span data-ttu-id="5d67f-128">KeepErrorReportForDays</span><span class="sxs-lookup"><span data-stu-id="5d67f-128">KeepErrorReportForDays</span></span>  <br/> |<span data-ttu-id="5d67f-129">Указывает число дней, в течение которого сохраняются отчеты об ошибках CDR; все отчеты старше указанного числа дней будут автоматически удаляться.</span><span class="sxs-lookup"><span data-stu-id="5d67f-129">Indicates the number of days that CDR error reports are kept; any reports older than the specified number of days will automatically be deleted.</span></span> <span data-ttu-id="5d67f-130">Отчеты об ошибках CDR — это диагностические отчеты, которые отправляются клиентскими приложениями, например Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="5d67f-130">CDR error reports are diagnostic reports uploaded by client applications such as Skype for Business Server.</span></span>  <br/> <span data-ttu-id="5d67f-131">В качестве значения этого свойства может быть установлено любое целое число от 1 до 2562 дней.</span><span class="sxs-lookup"><span data-stu-id="5d67f-131">You can set this property to any integer value between 1 and 2562 days.</span></span>  <br/> |<span data-ttu-id="5d67f-132">60 дней</span><span class="sxs-lookup"><span data-stu-id="5d67f-132">60 days</span></span>  <br/> |
   
<span data-ttu-id="5d67f-133">Аналогично, значения по умолчанию для некоторых параметров QoE показаны в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="5d67f-133">Similarly, default values for selected QoE settings are shown in this table:</span></span>
  
|<span data-ttu-id="5d67f-134">**Свойство**</span><span class="sxs-lookup"><span data-stu-id="5d67f-134">**Property**</span></span>|<span data-ttu-id="5d67f-135">**Описание**</span><span class="sxs-lookup"><span data-stu-id="5d67f-135">**Description**</span></span>|<span data-ttu-id="5d67f-136">**Значение по умолчанию**</span><span class="sxs-lookup"><span data-stu-id="5d67f-136">**Default Value**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="5d67f-137">EnableQoE</span><span class="sxs-lookup"><span data-stu-id="5d67f-137">EnableQoE</span></span>  <br/> |<span data-ttu-id="5d67f-p107">Указывает, включен ли мониторинг QoE. Если установлено значение True, то все записи QoE будут собираться и записываться в базу данных мониторинга.</span><span class="sxs-lookup"><span data-stu-id="5d67f-p107">Indicates whether or not QoE monitoring is enabled. If True, all QoE records will be collected and written to the monitoring database.</span></span>  <br/> |<span data-ttu-id="5d67f-140">True</span><span class="sxs-lookup"><span data-stu-id="5d67f-140">True</span></span>  <br/> |
|<span data-ttu-id="5d67f-141">EnablePurging</span><span class="sxs-lookup"><span data-stu-id="5d67f-141">EnablePurging</span></span>  <br/> |<span data-ttu-id="5d67f-p108">Указывает, будут ли записи QoE периодически удаляться из базы данных. Если установлено значение True, то записи будут удаляться после периода времени, заданного в свойстве KeepQoEDataForDays. Если параметр имеет значение False, то записи QoE будут сохраняться неопределенное время.</span><span class="sxs-lookup"><span data-stu-id="5d67f-p108">Indicates whether or not QoE records will periodically be deleted from the database. If True, records will be deleted after the time period specified by the KeepQoEDataForDays property. If False, QoE records will be maintained indefinitely.</span></span>  <br/> |<span data-ttu-id="5d67f-145">True</span><span class="sxs-lookup"><span data-stu-id="5d67f-145">True</span></span>  <br/> |
|<span data-ttu-id="5d67f-146">KeepQoEDataForDays</span><span class="sxs-lookup"><span data-stu-id="5d67f-146">KeepQoEDataForDays</span></span>  <br/> |<span data-ttu-id="5d67f-p109">Задает период в днях, в течение которого записи QoE будут сохраняться в базе данных; все записи старше заданного количества дней будут автоматически удаляться. Однако это будет происходить только в том случае, если включена очистка..</span><span class="sxs-lookup"><span data-stu-id="5d67f-p109">Indicates the number of days that QoE records will be kept in the database; any records older than the specified number of days will automatically be deleted. However, this will occur only if purging has been enabled.</span></span>  <br/> <span data-ttu-id="5d67f-149">В качестве значения этого свойства может быть установлено любое целое число от 1 до 2562 дней.</span><span class="sxs-lookup"><span data-stu-id="5d67f-149">KeepCallDetailForDays can be set to any integer value between 1 and 2562 days.</span></span>  <br/> |<span data-ttu-id="5d67f-150">60 дней</span><span class="sxs-lookup"><span data-stu-id="5d67f-150">60 days</span></span>  <br/> |
   
<span data-ttu-id="5d67f-151">Если требуется изменить эти глобальные параметры, то это можно сделать с помощью командлетов Set-CsCdrConfiguration и Set-CsQoEConfiguration.</span><span class="sxs-lookup"><span data-stu-id="5d67f-151">If you need to modify these global settings you can do so by using the Set-CsCdrConfiguration and the Set-CsQoEConfiguration cmdlets.</span></span> <span data-ttu-id="5d67f-152">Например, эта команда (выполнить из командной консоли Skype для бизнеса Server) отключает мониторинг CDR в глобальной области. Это можно сделать, задав для свойства Енаблекдр значение false ($False):</span><span class="sxs-lookup"><span data-stu-id="5d67f-152">For example, this command (run from within the Skype for Business Server Management Shell) disables CDR monitoring at the global scope; that's done by setting the EnableCDR property to False ($False):</span></span>
  
```
Set-CsCdrConfiguration -Identity "global" -EnableCDR $False
```

<span data-ttu-id="5d67f-153">Следует отметить, что отключение мониторинга не отделяет хранилище данных наблюдения от интерфейсного пула, не удаляет его и никаким другим образом не влияет на тыловую базу данных мониторинга.</span><span class="sxs-lookup"><span data-stu-id="5d67f-153">Note that disabling monitoring does not dissociate the monitoring store from the Front End pool, nor does it uninstall or otherwise affect the backend monitoring database.</span></span> <span data-ttu-id="5d67f-154">Если вы используете консоль управления Skype для бизнеса Server для отключения CDR или QoE, вы временно не сможете собирать и архивировать данные мониторинга в Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="5d67f-154">When you use Skype for Business Server Management Shell to disable either CDR or QoE monitoring all you really do is temporarily stop Skype for Business Server from collecting and archiving monitoring data.</span></span> <span data-ttu-id="5d67f-155">Чтобы возобновить сбор и архивацию, например, данных CDR, достаточно просто вернуть значение True ($True) свойству EnableCDR:</span><span class="sxs-lookup"><span data-stu-id="5d67f-155">If you want to resume, in this case, the collection and archiving of CDR data, all you need to do is set the EnableCDR property back to True ($True):</span></span>
  
```
Set-CsCdrConfiguration -Identity "global" -EnableCDR $True
```

<span data-ttu-id="5d67f-156">Аналогично, следующая команда отключает очистку записей QoE на глобальном уровне:</span><span class="sxs-lookup"><span data-stu-id="5d67f-156">Similarly, this command disables the purging of QoE records at the global scope:</span></span>
  
```
Set-CsQoEConfiguration -Identity "global" -EnablePurging $False
```

<span data-ttu-id="5d67f-p112">Помимо глобального уровня, параметры конфигурации CDR и QoE можно назначать на уровне сайта. Это обеспечивает дополнительную гибкость управления мониторингом; например, администратор может включить мониторинг CDR для сайта Redmond, но отключить мониторинг CDR для сайта Dublin. Для создания новых параметров конфигурации CDR на уровне сайта можно использовать команды, аналогичные следующей:</span><span class="sxs-lookup"><span data-stu-id="5d67f-p112">In addition to the global settings, CDR and QoE configurations settings can be assigned to the site scope. This provides additional management flexibility when it comes to monitoring; for example, an administrator can enable CDR monitoring for the Redmond site but disable CDR monitoring for the Dublin site. To create new CDR configuration settings at the site scope, use a command similar to this:</span></span>
  
```
New-CsCdrConfiguration -Identity "site:Redmond" -EnableCDR $False
```

<span data-ttu-id="5d67f-p113">Следует учитывать, что параметры, настроенные на уровне сайта, имеют преимущество перед параметрами, настроенными на глобальном уровне. Например, предположим, что мониторинг CDR включен на глобальном уровне, но отключен на уровне сайта для сайта Redmond. Это означает, что сведения регистрации вызовов для пользователей сайта Redmond не будут архивироваться. Однако для пользователей других сайтов (т.е. пользователей, которыми управляют глобальные настройки) сведения регистрации вызовов будут архивироваться.</span><span class="sxs-lookup"><span data-stu-id="5d67f-p113">Keep in mind that settings configured at the site scope take precedence over settings configured at the global scope. For example, suppose CDR monitoring is enabled at the global scope, but disabled at the site scope (for the Redmond site). That means that call detail recording information will not be archived for users in the Redmond site. However, users in other sites (that is, users managed by the global settings instead of the Redmond site settings) will have their call detail recording information archived.</span></span>
  
<span data-ttu-id="5d67f-164">Для создания новых параметров конфигурации QoE на уровне сайта можно использовать команды, аналогичные следующей:</span><span class="sxs-lookup"><span data-stu-id="5d67f-164">New QoE configuration settings can be created at the site scope by using a command like this one:</span></span>
  
```
New-CsQoEConfiguration -Identity "site:Redmond" -KeepQoEDataForDays 15
```

<span data-ttu-id="5d67f-165">Чтобы получить дополнительные сведения, введите в командной консоли Skype для Business Server следующие команды:</span><span class="sxs-lookup"><span data-stu-id="5d67f-165">For more information, type the following commands from within the Skype for Business Server Management Shell:</span></span>
  
```
Get-Help New-CsCdrConfiguration | more
Get-Help Set-CsCdrConfiguration | more
Get-Help New-CsQoEConfiguration | more
Get-Help Set-CsQoEConfiguration | more
```
