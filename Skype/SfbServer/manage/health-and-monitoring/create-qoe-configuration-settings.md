---
title: Создание параметров конфигурации качества взаимодействия в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 64f05569-07c7-4f76-a96b-ea4125a510d5
description: 'Сводка: сведения о параметрах качества взаимодействия (QoE) в Skype для бизнеса Server.'
ms.openlocfilehash: 254e6f1032026f715c30017f984bc2906f46e0df
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992796"
---
# <a name="create-quality-of-experience-configuration-settings-in-skype-for-business-server"></a><span data-ttu-id="9b033-103">Создание параметров конфигурации качества взаимодействия в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="9b033-103">Create Quality of Experience configuration settings in Skype for Business Server</span></span>
 
<span data-ttu-id="9b033-104">**Сводка:** Сведения о параметрах качества взаимодействия (QoE) в Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="9b033-104">**Summary:** Learn about Quality of Experience (QoE) settings in Skype for Business Server.</span></span>
  
<span data-ttu-id="9b033-p101">Показатели качества взаимодействия отслеживают качество аудио- и видеозвонков в вашей организации, включая число потерянных сетевых пакетов, фоновый шум и объем "дрожания" (разницы задержки пакетов). Эти показатели хранятся в базе данных отдельно от других данных (таких как записи функции регистрации вызовов), что позволяет включать и отключать запись качества взаимодействия независимо записи других данных.</span><span class="sxs-lookup"><span data-stu-id="9b033-p101">Quality of Experience (QoE) metrics track the quality of audio and video calls made in your organization, including such things as the number of network packets lost, background noise, and the amount of "jitter" (differences in packet delay). These metrics are stored in a database apart from other data (such as call detail records), which allows you to enable and disable QoE independent of other data recording.</span></span>
  
<span data-ttu-id="9b033-107">При установке Skype для бизнеса Server создается единая глобальная коллекция параметров конфигурации QoE.</span><span class="sxs-lookup"><span data-stu-id="9b033-107">When you install Skype for Business Server, a single, global collection of QoE configuration settings is created for you.</span></span> <span data-ttu-id="9b033-108">Администраторы также могут создавать особые параметры на уровне сайта.</span><span class="sxs-lookup"><span data-stu-id="9b033-108">Administrators also have the option of creating custom settings at the site scope.</span></span> <span data-ttu-id="9b033-109">При использовании эти параметров уровня сайта имеют приоритет над глобальными параметрами.</span><span class="sxs-lookup"><span data-stu-id="9b033-109">Whenever these site-scoped settings are used, they take precedence over the global settings.</span></span> <span data-ttu-id="9b033-110">Например, если созданы параметры уровня сайта для сайта Redmond, именно эти, а не глобальные параметры будут использоваться для управления качеством взаимодействия в сайте Redmond.</span><span class="sxs-lookup"><span data-stu-id="9b033-110">For example, if you create site-scoped settings for the Redmond site then those settings (rather than the global settings) will be used to manage QoE in Redmond.</span></span>
  
<span data-ttu-id="9b033-111">Параметры конфигурации QoE можно создать с помощью панели управления Skype для бизнеса Server или командлета [New-кскоеконфигуратион](https://docs.microsoft.com/powershell/module/skype/new-csqoeconfiguration?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="9b033-111">QoE configuration settings can be created by using either Skype for Business Server Control Panel or the [New-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csqoeconfiguration?view=skype-ps) cmdlet.</span></span> <span data-ttu-id="9b033-112">Если вы используете панель управления Skype для бизнеса Server для создания новых параметров, вам будут доступны следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="9b033-112">If you are using Skype for Business Server Control Panel to create new settings the following options will be available to you:</span></span>
  
|<span data-ttu-id="9b033-113">**Параметр пользовательского интерфейса**</span><span class="sxs-lookup"><span data-stu-id="9b033-113">**UI setting**</span></span>|<span data-ttu-id="9b033-114">**Параметр PowerShell**</span><span class="sxs-lookup"><span data-stu-id="9b033-114">**PowerShell parameter**</span></span>|<span data-ttu-id="9b033-115">**Описание**</span><span class="sxs-lookup"><span data-stu-id="9b033-115">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="9b033-116">Имя</span><span class="sxs-lookup"><span data-stu-id="9b033-116">Name</span></span>  <br/> |<span data-ttu-id="9b033-117">Identity</span><span class="sxs-lookup"><span data-stu-id="9b033-117">Identity</span></span>  <br/> |<span data-ttu-id="9b033-p104">Уникальный идентификатор создаваемых параметров. Параметры конфигурации качества взаимодействия могут быть созданы только на уровне сайта.</span><span class="sxs-lookup"><span data-stu-id="9b033-p104">Unique identifier for the settings to be created. QoE configuration settings can only be created at the site scope.</span></span>  <br/> |
|<span data-ttu-id="9b033-120">Разрешить отслеживание данных о качестве связи</span><span class="sxs-lookup"><span data-stu-id="9b033-120">Enable monitoring of QoE data</span></span>  <br/> |<span data-ttu-id="9b033-121">EnableQoE</span><span class="sxs-lookup"><span data-stu-id="9b033-121">EnableQoE</span></span>  <br/> |<span data-ttu-id="9b033-122">Указывает, будут ли записи качества взаимодействия собраны и сохранены в базу данных мониторинга.</span><span class="sxs-lookup"><span data-stu-id="9b033-122">Specifies whether QoE records will be collected and saved to the monitoring database.</span></span>  <br/> |
|<span data-ttu-id="9b033-123">Разрешить очистку данных о качестве связи</span><span class="sxs-lookup"><span data-stu-id="9b033-123">Enable purging of QoE data</span></span>  <br/> |<span data-ttu-id="9b033-124">EnablePurging</span><span class="sxs-lookup"><span data-stu-id="9b033-124">EnablePurging</span></span>  <br/> |<span data-ttu-id="9b033-125">Определяет, можно ли очищать записи после истечения периода времени, определенного в свойстве **Хранить данные о качестве взаимодействия не дольше (дн.)**.</span><span class="sxs-lookup"><span data-stu-id="9b033-125">Specifies whether records will be purged after the duration defined in the **Keep QoE data for a maximum duration (days)** property has elapsed.</span></span> <br/> |
|<span data-ttu-id="9b033-126">Хранить данные о качестве взаимодействия не дольше (дн.):</span><span class="sxs-lookup"><span data-stu-id="9b033-126">Keep QoE data for maximum duration (days)</span></span>  <br/> |<span data-ttu-id="9b033-127">KeepQoEDataForDays</span><span class="sxs-lookup"><span data-stu-id="9b033-127">KeepQoEDataForDays</span></span>  <br/> |<span data-ttu-id="9b033-p105">Число дней хранения данных о качестве взаимодействия до удаления из базы данных. Это значение игнорируется, если очистка отключена.</span><span class="sxs-lookup"><span data-stu-id="9b033-p105">Number of days QoE data will be stored before being purged from the database. This value is ignored if purging is disabled.</span></span>  <br/> |
   
> [!NOTE]
> <span data-ttu-id="9b033-130">Командлет New-Кскоеконфигуратион содержит дополнительные параметры, недоступные на панели управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="9b033-130">The New-CsQoEConfiguration cmdlet includes additional options not available in Skype for Business Server Control Panel.</span></span> <span data-ttu-id="9b033-131">Дополнительные сведения можно найти в разделе справки, посвященных [новым кскоеконфигуратион](https://docs.microsoft.com/powershell/module/skype/new-csqoeconfiguration?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="9b033-131">For more information, see the [New-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csqoeconfiguration?view=skype-ps) help topic.</span></span>
  
### <a name="to-create-qoe-configuration-settings-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="9b033-132">Создание параметров конфигурации QoE с помощью панели управления "Skype для бизнеса Server"</span><span class="sxs-lookup"><span data-stu-id="9b033-132">To create QoE configuration settings by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="9b033-p107">Войдите на компьютер как член группы RTCUniversalServerAdmins или роли CsVoiceAdministrator, CsServerAdministrator или CsAdministrator. Дополнительные сведения см. в разделе **Delegate Setup Permissions**.</span><span class="sxs-lookup"><span data-stu-id="9b033-p107">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role. For details, see **Delegate Setup Permissions**.</span></span>
    
2. <span data-ttu-id="9b033-135">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="9b033-135">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="9b033-136">В левой панели навигации щелкните **Мониторинг и архивация** и затем выберите **Данные о качестве взаимодействия**.</span><span class="sxs-lookup"><span data-stu-id="9b033-136">In the left navigation bar, click **Monitoring and Archiving**, and then click **Quality of Experience Data**.</span></span>
    
4. <span data-ttu-id="9b033-137">На странице **Данные качества взаимодействия** нажмите кнопку **Создать**.</span><span class="sxs-lookup"><span data-stu-id="9b033-137">On the **Quality of Experience Data** page, click **New**.</span></span>
    
5. <span data-ttu-id="9b033-138">В разделе **Выбор сайта** щелкните сайт, к которому должна применяться эта политика, и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="9b033-138">In **Select a Site**, click the site to which the policy is to be applied, and click **OK**.</span></span>
    
6. <span data-ttu-id="9b033-139">На странице **Новый параметр качества обслуживания** сделайте следующее.</span><span class="sxs-lookup"><span data-stu-id="9b033-139">In **New Quality of Experience Setting**, do the following:</span></span>
    
   - <span data-ttu-id="9b033-140">Выберите пункт **Включить мониторинг данных качества обслуживания (CDR)**, чтобы включить мониторинг.</span><span class="sxs-lookup"><span data-stu-id="9b033-140">Select **Enable monitoring of QoE data** to turn on monitoring.</span></span>
    
   - <span data-ttu-id="9b033-141">Выберите пункт **Включить очистку данных качества обслуживания (CDR)**.</span><span class="sxs-lookup"><span data-stu-id="9b033-141">Select **Enable purging of QoE data** to turn on purging.</span></span>
    
   - <span data-ttu-id="9b033-142">В поле **Хранить записи сведений о звонках в течение (дней)** выберите максимальное количество дней, в течение которого должны храниться записи сведений о звонках.</span><span class="sxs-lookup"><span data-stu-id="9b033-142">In **Keep QoE for maximum duration (days)**, select the maximum number of days that QoE records should be retained.</span></span>
    
7. <span data-ttu-id="9b033-143">Нажмите **Исполнить**.</span><span class="sxs-lookup"><span data-stu-id="9b033-143">Click **Commit**.</span></span>
    
## <a name="creating-qoe-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="9b033-144">Создание параметров конфигурации QoE с помощью командлетов Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="9b033-144">Creating QoE Configuration Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="9b033-145">Вы можете создавать параметры конфигурации QoE с помощью Windows PowerShell и командлета New-Кскоеконфигуратион.</span><span class="sxs-lookup"><span data-stu-id="9b033-145">You can create QoE configuration settings by using Windows PowerShell and the New-CsQoEConfiguration cmdlet.</span></span> <span data-ttu-id="9b033-146">Этот командлет можно выполнить либо из командной консоли Skype для бизнеса Server, либо из удаленного сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9b033-146">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="9b033-147">Дополнительные сведения об использовании удаленной оболочки Windows PowerShell для подключения к серверу Skype для бизнеса можно найти в статье ["Краткое руководство": Управление Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell](https://go.microsoft.com/fwlink/p/?linkId=255876).</span><span class="sxs-lookup"><span data-stu-id="9b033-147">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="9b033-148">Этот процесс одинаков в Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="9b033-148">The process is the same in Skype for Business Server.</span></span>
  
### <a name="to-create-a-new-collection-of-qoe-configuration-settings"></a><span data-ttu-id="9b033-149">Чтобы создать новую коллекцию параметров конфигурации качества взаимодействия</span><span class="sxs-lookup"><span data-stu-id="9b033-149">To create a new collection of QoE configuration settings</span></span>

 <span data-ttu-id="9b033-150">Эта команда создает новую коллекцию параметров конфигурации качества взаимодействия, применяемую на сайте Redmond:</span><span class="sxs-lookup"><span data-stu-id="9b033-150">This command creates a new collection of QoE configuration settings applied to the Redmond site:</span></span>
    
  ```PowerShell
  New-CsQoEConfiguration -Identity "site:Redmond"
  ```

### <a name="to-create-a-new-collection-of-qoe-configuration-settings-where-qoe-monitoring-is-disabled"></a><span data-ttu-id="9b033-151">Чтобы создать новую коллекцию параметров конфигурации качества взаимодействия при отключенном мониторинге качества взаимодействия</span><span class="sxs-lookup"><span data-stu-id="9b033-151">To create a new collection of QoE configuration settings where QoE monitoring is disabled</span></span>

 <span data-ttu-id="9b033-p109">Так как никакие параметры (кроме обязательного параметра Identity) не были указаны в приведенных ранее командах, новая коллекция параметров конфигурации будет использовать значения по умолчанию для всех своих свойств. Чтобы создать параметры, использующие другие значения свойств просто включите соответствующий параметр и его значение. Например, чтобы создать коллекцию параметров конфигурации качества взаимодействия, которые, по умолчанию, разрешают отключать запись качества взаимодействия, используйте следующую команду:</span><span class="sxs-lookup"><span data-stu-id="9b033-p109">Because no parameters (other than the mandatory Identity parameter) were specified in the preceding command, the new collection of configuration settings will use the default values for all its properties. To create settings that use different property values, simply include the appropriate parameter and parameter value. For example, to create a collection of Quality of Experience configuration settings that, by default, allow disable QoE recording use a command like this:</span></span>
    
  ```PowerShell
  New-CsQoEConfiguration -Identity "site:Redmond" -EnableQoE $False
  ```

### <a name="to-specify-multiple-property-values-when-creating-a-new-collection-of-qoe-configuration-settings"></a><span data-ttu-id="9b033-155">Чтобы указать значения нескольких свойств при создании новой коллекции параметров конфигурации качества взаимодействия</span><span class="sxs-lookup"><span data-stu-id="9b033-155">To specify multiple property values when creating a new collection of QoE configuration settings</span></span>

 <span data-ttu-id="9b033-p110">Можно задать несколько значений свойств, включив несколько параметров. Например, эта команда настраивает новые параметры для сохранения данных качества взаимодействия в течение 30 дней и очистки старых данных в 3:00:</span><span class="sxs-lookup"><span data-stu-id="9b033-p110">You can multiple property values by including multiple parameters. For example, this command configures the new settings to keep QoE data for 30 days and to purge old data at 3:00 AM:</span></span>
    
  ```PowerShell
  New-CsQoEConfiguration -Identity "site:Redmond" -KeepQoEDataForDays 30 -PurgeHourOfDay 3
  ```

<span data-ttu-id="9b033-158">Дополнительные сведения можно найти в разделе справки по командлету [New-кскоеконфигуратион](https://docs.microsoft.com/powershell/module/skype/new-csqoeconfiguration?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="9b033-158">For more information, see the help topic for the [New-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csqoeconfiguration?view=skype-ps) cmdlet.</span></span>
  

