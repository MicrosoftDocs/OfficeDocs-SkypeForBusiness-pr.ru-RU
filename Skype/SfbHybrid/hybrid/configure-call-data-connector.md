---
title: Настройка соединителя данных вызовов
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: Инструкции по настройке соединителя данных вызовов, которые позволяют просматривать телеметрию из локальной сети Skype для бизнеса с помощью средств Skype для бизнеса Online.
ms.openlocfilehash: 4d472ce49a3059df7286c647b013abe321b9fd15
ms.sourcegitcommit: afc7edd03f4baa1d75f9642d4dbce767fec69b00
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "40963047"
---
# <a name="configure-call-data-connector"></a><span data-ttu-id="4f5a0-103">Настройка соединителя данных вызовов</span><span class="sxs-lookup"><span data-stu-id="4f5a0-103">Configure Call Data Connector</span></span>

<span data-ttu-id="4f5a0-104">В этой статье описывается настройка соединителя данных вызовов (один набор инструментов), позволяющий просматривать данные качества звонков Skype для бизнеса Server с помощью панели мониторинга качества звонков в Skype для бизнеса Online (CQD) и средства анализа вызовов (CA).</span><span class="sxs-lookup"><span data-stu-id="4f5a0-104">This article describes how to configure Call Data Connector--a single toolset that enables viewing Skype for Business Server Call Quality Data using Skype for Business Online Call Quality Dashboard (CQD) and Call Analytics (CA) tools.</span></span>

<span data-ttu-id="4f5a0-105">Дополнительные сведения о преимуществах и преимуществах соединителей данных вызовов, таких как требования к роли и настройка гибридного подключения, приведены в статье [Plan Call Data Connector](plan-call-data-connector.md).</span><span class="sxs-lookup"><span data-stu-id="4f5a0-105">For more information about Call Data Connector benefits and pre-requisites, such as role requirements and setting up hybrid connectivity, see [Plan Call Data Connector](plan-call-data-connector.md).</span></span>

## <a name="enable-monitoring"></a><span data-ttu-id="4f5a0-106">Включение мониторинга</span><span class="sxs-lookup"><span data-stu-id="4f5a0-106">Enable Monitoring</span></span>
 
<span data-ttu-id="4f5a0-107">Необходимо настроить сбор данных о вызовах (CDR) и качества взаимодействия (QoE) в мониторинге пула переднего плана с локальными базами данных LCSCdr и QoEMetrics; в противном случае информационные панели анализа вызовов и качества звонков не будут работать с данными.</span><span class="sxs-lookup"><span data-stu-id="4f5a0-107">You must configure Call Data Recording (CDR) and Quality of Experience (QoE) data collection in your front end pool Monitoring,with local LCSCdr and QoEMetrics databases; otherwise, the Call Analytics and Call Quality Dashboards won’t get data to work with.</span></span> <span data-ttu-id="4f5a0-108">Перед настройкой соединителя данных вызовов выполните действия, описанные в разделе [deploy Monitoring in Skype для бизнеса Server](../../SfbServer/deploy/deploy-monitoring/deploy-monitoring.md) , чтобы настроить как CDR, так и QoE, а также базовый мониторинг.</span><span class="sxs-lookup"><span data-stu-id="4f5a0-108">Before you Configure Call Data Connector, follow the steps provided in [Deploy monitoring in Skype for Business Server](../../SfbServer/deploy/deploy-monitoring/deploy-monitoring.md) to configure both CDR and QoE as well as basic Monitoring.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="4f5a0-109">Соединитель данных вызовов не будет работать, если мониторинг не включен в интерфейсном пуле.</span><span class="sxs-lookup"><span data-stu-id="4f5a0-109">Call Data Connector will not function if Monitoring is not enabled on the front end pool.</span></span>

## <a name="enable-call-data-connector"></a><span data-ttu-id="4f5a0-110">Включить соединитель данных вызовов</span><span class="sxs-lookup"><span data-stu-id="4f5a0-110">Enable Call Data Connector</span></span>

<span data-ttu-id="4f5a0-111">Чтобы настроить и включить соединитель данных вызовов, необходимо использовать следующие командлеты:</span><span class="sxs-lookup"><span data-stu-id="4f5a0-111">To configure and enable Call Data Connector, you will use the following cmdlets:</span></span>

| <span data-ttu-id="4f5a0-112">Командлет</span><span class="sxs-lookup"><span data-stu-id="4f5a0-112">Cmdlet</span></span>| <span data-ttu-id="4f5a0-113">Описание</span><span class="sxs-lookup"><span data-stu-id="4f5a0-113">Description</span></span>|
| :-----------------|---------------:|
| <span data-ttu-id="4f5a0-114">New — Ксклаудкаллдатаконнектион</span><span class="sxs-lookup"><span data-stu-id="4f5a0-114">New-CsCloudCallDataConnection</span></span> | <span data-ttu-id="4f5a0-115">Сетевой командлет, который устанавливает сборщик данных в сети.</span><span class="sxs-lookup"><span data-stu-id="4f5a0-115">An online cmdlet that establishes an online data collector.</span></span>|
| <span data-ttu-id="4f5a0-116">Get — Ксклаудкаллдатаконнектион</span><span class="sxs-lookup"><span data-stu-id="4f5a0-116">Get-CsCloudCallDataConnection</span></span> | <span data-ttu-id="4f5a0-117">Оперативный командлет, который получает существующий веб-сборщик данных.</span><span class="sxs-lookup"><span data-stu-id="4f5a0-117">An online cmdlet that retrieves an existing online data collector.</span></span>|  
| <span data-ttu-id="4f5a0-118">Get — Ксклаудкаллдатаконнектор</span><span class="sxs-lookup"><span data-stu-id="4f5a0-118">Get-CsCloudCallDataConnector</span></span> | <span data-ttu-id="4f5a0-119">Локальный Командлет, который получает сведения о подключении, созданные командлетом New – Ксклаудкаллдатаконнектион.</span><span class="sxs-lookup"><span data-stu-id="4f5a0-119">An on-premises cmdlet that retrieves the connection information created by the New-CsCloudCallDataConnection cmdlet.</span></span> |
| <span data-ttu-id="4f5a0-120">Set — Ксклаудкаллдатаконнектор</span><span class="sxs-lookup"><span data-stu-id="4f5a0-120">Set-CsCloudCallDataConnector</span></span> | <span data-ttu-id="4f5a0-121">Локальный Командлет, сохраняющий локальную копию сведений о подключении, созданную командлетом New – Ксклаудкаллдатаконнектион.</span><span class="sxs-lookup"><span data-stu-id="4f5a0-121">An on-premises cmdlet that saves an on-premises copy of the connection information created by the New-CsCloudCallDataConnection cmdlet.</span></span> |  
| <span data-ttu-id="4f5a0-122">Set — Ксклаудкаллдатаконнекторконфигуратион</span><span class="sxs-lookup"><span data-stu-id="4f5a0-122">Set-CsCloudCallDataConnectorConfiguration</span></span> | <span data-ttu-id="4f5a0-123">Локальный Командлет, который позволяет включать или отключать соединитель и настраивать уровень области.</span><span class="sxs-lookup"><span data-stu-id="4f5a0-123">An on-premises cmdlet that allows you to enable or disable the connector and customize the scope level.</span></span>|

> [!NOTE]
> <span data-ttu-id="4f5a0-124">Чтобы стереть конфигурацию и начать заново, используйте командлет Remove – ксклауддатконнекторконфигуратион.</span><span class="sxs-lookup"><span data-stu-id="4f5a0-124">To erase your configuration and start over, please use the Remove-csclouddatconnectorconfiguration cmdlet.</span></span>

### <a name="configure-your-environment"></a><span data-ttu-id="4f5a0-125">Настройка среды</span><span class="sxs-lookup"><span data-stu-id="4f5a0-125">Configure your environment</span></span> 

<span data-ttu-id="4f5a0-126">Чтобы настроить среду для включения сборщика данных в Интернете, сначала необходимо войти в Skype для бизнеса Online PowerShell от имени администратора.</span><span class="sxs-lookup"><span data-stu-id="4f5a0-126">To configure your environment to enable an online data collector, you must first log in to Skype for Business Online PowerShell as an administrator.</span></span> <span data-ttu-id="4f5a0-127">Дополнительные сведения можно найти [в статье Управление Skype для бизнеса Online с помощью Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell).</span><span class="sxs-lookup"><span data-stu-id="4f5a0-127">For more information, see [Manage Skype for Business Online with Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell).</span></span>

<span data-ttu-id="4f5a0-128">Существует два способа входа в Skype для бизнеса Online PowerShell:</span><span class="sxs-lookup"><span data-stu-id="4f5a0-128">There are two methods for logging in to Skype for Business Online PowerShell:</span></span>

- <span data-ttu-id="4f5a0-129">В командной консоли Skype для бизнеса Server 2019 (рекомендуемый способ)</span><span class="sxs-lookup"><span data-stu-id="4f5a0-129">From the Skype for Business Server 2019 management shell (recommended method)</span></span>
- <span data-ttu-id="4f5a0-130">Из другого сеанса PowerShell</span><span class="sxs-lookup"><span data-stu-id="4f5a0-130">From another PowerShell session</span></span>

#### <a name="log-in-to-skype-for-business-online-powershell-from-the-skype-for-business-server-management-shell-recommended-method"></a><span data-ttu-id="4f5a0-131">Вход в Skype для бизнеса Online PowerShell из командной консоли Skype для бизнеса Server (рекомендуемый способ)</span><span class="sxs-lookup"><span data-stu-id="4f5a0-131">Log in to Skype for Business Online PowerShell from the Skype for Business Server management shell (recommended method)</span></span>

1. <span data-ttu-id="4f5a0-132">При первом запуске соединителя выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="4f5a0-132">If enabling the connector for the first time, run the following command:</span></span>

   ```PowerShell
   New-CsCloudCallDataConnection | Set-CsCloudCallDataConnector -TenantId <tenant_id>
   ```

2. <span data-ttu-id="4f5a0-133">Если возникнет сообщение об ошибке, что подключение уже существует, это означает, что подключение к данным вызова уже существует для вашего клиента.</span><span class="sxs-lookup"><span data-stu-id="4f5a0-133">If you get an error that the connection already exists, this means that the call data connection already exists for your tenant.</span></span> <span data-ttu-id="4f5a0-134">В этом случае выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="4f5a0-134">In this case, run the command:</span></span> 

   ```PowerShell
   Get-CsCloudCallDataConnection | Set-CsCloudCallDataConnector -TenantId <tenant_id>
   ```


#### <a name="log-in-to-skype-for-business-online-powershell-from-another-powershell-session-optional-method"></a><span data-ttu-id="4f5a0-135">Вход в Skype для бизнеса Online PowerShell из другого сеанса PowerShell (необязательный метод)</span><span class="sxs-lookup"><span data-stu-id="4f5a0-135">Log in to Skype for Business Online PowerShell from another PowerShell session (optional method)</span></span>

1.  <span data-ttu-id="4f5a0-136">При первом запуске соединителя выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="4f5a0-136">If enabling the connector for the first time, run the following command:</span></span> 

    ```PowerShell 
    New-CsCloudCallDataConnection 
    ```

2.  <span data-ttu-id="4f5a0-137">Если возникнет сообщение об ошибке, что подключение уже существует, это означает, что подключение к данным вызова уже существует для вашего клиента.</span><span class="sxs-lookup"><span data-stu-id="4f5a0-137">If you get an error that the connection already exists, this means that the call data connection already exists for your tenant.</span></span> <span data-ttu-id="4f5a0-138">В этом случае выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="4f5a0-138">In this case, run the command:</span></span> 

    ```PowerShell
    Get-CsCloudCallDataConnection  
    ```

<span data-ttu-id="4f5a0-139">Выходные данные вышеуказанных команд содержат значение маркера, которое потребуется при настройке локальной среды следующим образом:</span><span class="sxs-lookup"><span data-stu-id="4f5a0-139">The output of the above commands contains a token value, which you will need when configuring your on-premises environment as follows:</span></span>

<span data-ttu-id="4f5a0-140">В командной консоли Skype для бизнеса Server укажите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="4f5a0-140">From within the Skype for Business Server management shell, specify the following command:</span></span>

```PowerShell
Set-CsCloudCallDataConnector -Identity Global -TenantId <tenant_id> -Token <token-copied-from-online>
```

### <a name="configure-the-scope"></a><span data-ttu-id="4f5a0-141">Настройка области</span><span class="sxs-lookup"><span data-stu-id="4f5a0-141">Configure the scope</span></span>

<span data-ttu-id="4f5a0-142">Вы можете включить соединитель данных вызовов для определенного сайта или для всего развертывания Skype для бизнеса Server с помощью командлета Set-Ксклаудкаллдатаконнекторконфигуратион в командной консоли Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="4f5a0-142">You can enable Call Data Connector for a particular site or for your entire Skype for Business Server deployment by using the Set-CsCloudCallDataConnectorConfiguration cmdlet from within the Skype for Business Server management shell.</span></span> <span data-ttu-id="4f5a0-143">Например, следующая команда включает соединитель данных вызова в глобальной области:</span><span class="sxs-lookup"><span data-stu-id="4f5a0-143">For example, the following command enables Call Data Connector at the global scope:</span></span>

```PowerShell
Set-CsCloudCallDataConnectorConfiguration -Identity "global" -EnableCallDataConnector $True
```

<span data-ttu-id="4f5a0-144">В дополнение к глобальным параметрам параметры конфигурации соединителя данных могут быть назначены для области сайта.</span><span class="sxs-lookup"><span data-stu-id="4f5a0-144">In addition to the global settings, Call Data Connector configuration settings can be assigned to the site scope.</span></span> <span data-ttu-id="4f5a0-145">Это обеспечивает дополнительную гибкость управления, когда дело доходит до мониторинга.</span><span class="sxs-lookup"><span data-stu-id="4f5a0-145">This provides additional management flexibility when it comes to monitoring.</span></span> <span data-ttu-id="4f5a0-146">Например, администратор может включить переадресацию соединителя данных вызовов для сайта Redmond, но отключить переадресацию соединителя данных вызовов для сайта Dublin, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="4f5a0-146">For example, an administrator can enable Call Data Connector forwarding for the Redmond site but disable Call Data Connector forwarding for the Dublin site, as shown in the following example:</span></span>

```PowerShell
Set-CsCloudCallDataConnectorConfiguration -Identity "site:Redmond" -EnableCallDataConnector $True
```

```PowerShell
Set-CsCloudCallDataConnectorConfiguration -Identity "site:Dublin" -EnableCallDataConnector $False
```

<span data-ttu-id="4f5a0-147">Параметры, настроенные в области сайта, имеют приоритет над параметрами, настроенными в глобальной области.</span><span class="sxs-lookup"><span data-stu-id="4f5a0-147">Settings configured at the site scope take precedence over settings configured at the global scope.</span></span> <span data-ttu-id="4f5a0-148">Например, предположим, что переадресация соединителя данных вызовов включена в глобальной области, но отключена на уровне сайта (для сайта Redmond).</span><span class="sxs-lookup"><span data-stu-id="4f5a0-148">For example, suppose Call Data Connector forwarding is enabled at the global scope, but disabled at the site scope (for the Redmond site).</span></span> <span data-ttu-id="4f5a0-149">Это означает, что сведения о регистрации вызовов и QoE не будут пересылаться для пользователей на сайте Redmond.</span><span class="sxs-lookup"><span data-stu-id="4f5a0-149">That means that call detail recording and QoE information will not be forwarded for users in the Redmond site.</span></span> <span data-ttu-id="4f5a0-150">Тем не менее, для пользователей на других сайтах (то есть для пользователей, управляемых глобальными параметрами, а не с параметрами сайта Redmond), записываются сведения о вызовах и пересылаются сведения о QoE.</span><span class="sxs-lookup"><span data-stu-id="4f5a0-150">However, users in other sites (that is, users managed by the global settings instead of the Redmond site settings) will have their call detail recording and QoE information forwarded.</span></span>

<span data-ttu-id="4f5a0-151">Значения наиболее часто используемых параметров соединителя данных вызовов показаны в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="4f5a0-151">Values for the most commonly used settings used by Call Data Connector are shown in the following table:</span></span>  

|<span data-ttu-id="4f5a0-152">Свойство</span><span class="sxs-lookup"><span data-stu-id="4f5a0-152">Property</span></span>|<span data-ttu-id="4f5a0-153">Описание</span><span class="sxs-lookup"><span data-stu-id="4f5a0-153">Description</span></span>|<span data-ttu-id="4f5a0-154">Значение по умолчанию</span><span class="sxs-lookup"><span data-stu-id="4f5a0-154">Default value</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="4f5a0-155">енаблекаллдатаконнектор</span><span class="sxs-lookup"><span data-stu-id="4f5a0-155">EnableCallDataConnector</span></span>  <br/> |<span data-ttu-id="4f5a0-156">Указывает, включен ли соединитель данных вызовов.</span><span class="sxs-lookup"><span data-stu-id="4f5a0-156">Indicates whether Call Data Connector is enabled.</span></span> <span data-ttu-id="4f5a0-157">Если задано значение true, записи мониторинга будут пересылаться в оперативный мониторинг.</span><span class="sxs-lookup"><span data-stu-id="4f5a0-157">If True, monitoring records will be forwarded to online monitoring.</span></span>  <br/> |<span data-ttu-id="4f5a0-158">$False</span><span class="sxs-lookup"><span data-stu-id="4f5a0-158">$False</span></span>  <br/> |
| <span data-ttu-id="4f5a0-159">Удостоверение</span><span class="sxs-lookup"><span data-stu-id="4f5a0-159">Identity</span></span> | <span data-ttu-id="4f5a0-160">Определяет уровень области для команды: глобальная или site.</span><span class="sxs-lookup"><span data-stu-id="4f5a0-160">Determines the scope level for the command: global or site.</span></span>   | <span data-ttu-id="4f5a0-161">глобального</span><span class="sxs-lookup"><span data-stu-id="4f5a0-161">global</span></span>  |

## <a name="disable-call-data-connector"></a><span data-ttu-id="4f5a0-162">Отключить соединитель данных вызовов</span><span class="sxs-lookup"><span data-stu-id="4f5a0-162">Disable Call Data Connector</span></span>

<span data-ttu-id="4f5a0-163">Отключение соединителя данных вызовов не приводит к удалению хранилища мониторинга из пула переднего плана, а также удалению или невозможности влияния на внутреннюю базу данных мониторинга.</span><span class="sxs-lookup"><span data-stu-id="4f5a0-163">Disabling Call Data Connector does not disassociate the monitoring store from the Front End pool, nor does it uninstall or otherwise affect the backend monitoring database.</span></span> <span data-ttu-id="4f5a0-164">Когда вы отключаете соединитель данных вызовов, вы останавливаете Skype для бизнеса Server на отправку данных о вызовах в облако.</span><span class="sxs-lookup"><span data-stu-id="4f5a0-164">When you disable Call Data Connector, you stop Skype for Business Server from uploading call data to the cloud.</span></span> 

<span data-ttu-id="4f5a0-165">Вы отключаете соединитель данных вызовов с помощью командлета Set-Ксклаудкаллдатаконнекторконфигуратион в командной консоли Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="4f5a0-165">You disable Call Data Connector by using the Set-CsCloudCallDataConnectorConfiguration cmdlet from within the Skype for Business Server management shell.</span></span> <span data-ttu-id="4f5a0-166">Например, следующая команда отключает соединитель данных вызова в глобальной области, присвоив свойству Енаблекаллдатаконнектор значение $False:</span><span class="sxs-lookup"><span data-stu-id="4f5a0-166">For example, the following command disables Call Data Connector at the global scope by setting the EnableCallDataConnector property to $False:</span></span>

```PowerShell
Set-CsCloudCallDataConnectorConfiguration -Identity "global" -EnableCallDataConnector $False
```

<span data-ttu-id="4f5a0-167">Если вы хотите возобновить передачу данных вызовов в облако, присвойте свойству Енаблекаллдатаконнектор значение $True, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="4f5a0-167">If you want to resume uploading call data to the cloud, set the EnableCallDataConnector property back to $True, as shown in the following example:</span></span>

```PowerShell
Set-CsCloudCallDataConnectorConfiguration -Identity "global" -EnableCallDataConnector $True
```

## <a name="view-on-premises-data-through-the-online-dashboard"></a><span data-ttu-id="4f5a0-168">Просмотр локальных данных через веб-панель мониторинга</span><span class="sxs-lookup"><span data-stu-id="4f5a0-168">View on-premises data through the online dashboard</span></span>

 <span data-ttu-id="4f5a0-169">После включения соединителя данных вызовов вы можете просматривать данные локального вызова на панели мониторинга анализа вызовов или панели мониторинга качества вызовов, как описано в статье [использование аналитики вызовов для устранения неполадок](https://docs.microsoft.com/skypeforbusiness/using-call-quality-in-your-organization/use-call-analytics-to-troubleshoot-poor-call-quality) , а также [для включения и использования панели мониторинга качества звонков для Microsoft Teams и Skype для бизнеса Online](/MicrosoftTeams/turning-on-and-using-call-quality-dashboard).</span><span class="sxs-lookup"><span data-stu-id="4f5a0-169">After Call Data Connector is enabled, you can view your on-premises call data on the Call Analytics dashboard or Call Quality Dashboard as described in  [Use Call Analytics to troubleshoot poor quality](https://docs.microsoft.com/skypeforbusiness/using-call-quality-in-your-organization/use-call-analytics-to-troubleshoot-poor-call-quality) and [Turn on and use Call Quality Dashboard for Microsoft Teams and Skype for Business Online](/MicrosoftTeams/turning-on-and-using-call-quality-dashboard).</span></span>

## <a name="for-more-information"></a><span data-ttu-id="4f5a0-170">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="4f5a0-170">For more information</span></span>

<span data-ttu-id="4f5a0-171">Для получения дополнительных сведений о командлетах можно использовать команду Get-Help в командной консоли Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="4f5a0-171">For more information on the cmdlets, you can use the Get-Help command from the Skype for Business Server Management Shell.</span></span> <span data-ttu-id="4f5a0-172">Пример:</span><span class="sxs-lookup"><span data-stu-id="4f5a0-172">For example:</span></span>

<span data-ttu-id="4f5a0-173">Get – Help Get – Ксклаудкаллдатаконнектор | превышает</span><span class="sxs-lookup"><span data-stu-id="4f5a0-173">Get-Help Get-CsCloudCallDataConnector | more</span></span>

<span data-ttu-id="4f5a0-174">Get – Help Set — Ксклаудкаллдатаконнектор | превышает</span><span class="sxs-lookup"><span data-stu-id="4f5a0-174">Get-Help Set-CsCloudCallDataConnector | more</span></span>

<span data-ttu-id="4f5a0-175">Get – Help Set — Ксклаудкаллдатаконнекторконфигуратион | превышает</span><span class="sxs-lookup"><span data-stu-id="4f5a0-175">Get-Help Set-CsCloudCallDataConnectorConfiguration | more</span></span>
