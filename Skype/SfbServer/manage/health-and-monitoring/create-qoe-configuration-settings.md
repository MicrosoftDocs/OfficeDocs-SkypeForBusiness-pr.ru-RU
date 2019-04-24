---
title: Создание параметров конфигурации качества взаимодействия в Скайп для Business Server
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 64f05569-07c7-4f76-a96b-ea4125a510d5
description: 'Сводка: Сведения о параметрах качества взаимодействия (QoE) в Скайп для Business Server.'
ms.openlocfilehash: 971d3488d0c6d20586e33424c1fbb2b197b31241
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "32198241"
---
# <a name="create-quality-of-experience-configuration-settings-in-skype-for-business-server"></a><span data-ttu-id="9cc1e-103">Создание параметров конфигурации качества взаимодействия в Скайп для Business Server</span><span class="sxs-lookup"><span data-stu-id="9cc1e-103">Create Quality of Experience configuration settings in Skype for Business Server</span></span>
 
<span data-ttu-id="9cc1e-104">**Сводка:** Сведения о параметрах качества взаимодействия (QoE) в Скайп для Business Server.</span><span class="sxs-lookup"><span data-stu-id="9cc1e-104">**Summary:** Learn about Quality of Experience (QoE) settings in Skype for Business Server.</span></span>
  
<span data-ttu-id="9cc1e-p101">Показатели качества взаимодействия отслеживают качество аудио- и видеозвонков в вашей организации, включая число потерянных сетевых пакетов, фоновый шум и объем "дрожания" (разницы задержки пакетов). Эти показатели хранятся в базе данных отдельно от других данных (таких как записи функции регистрации вызовов), что позволяет включать и отключать запись качества взаимодействия независимо записи других данных.</span><span class="sxs-lookup"><span data-stu-id="9cc1e-p101">Quality of Experience (QoE) metrics track the quality of audio and video calls made in your organization, including such things as the number of network packets lost, background noise, and the amount of "jitter" (differences in packet delay). These metrics are stored in a database apart from other data (such as call detail records), which allows you to enable and disable QoE independent of other data recording.</span></span>
  
<span data-ttu-id="9cc1e-107">Когда вы устанавливаете Скайп для Business Server, single, глобальной коллекции параметров конфигурации качества взаимодействия будет создан автоматически.</span><span class="sxs-lookup"><span data-stu-id="9cc1e-107">When you install Skype for Business Server, a single, global collection of QoE configuration settings is created for you.</span></span> <span data-ttu-id="9cc1e-108">Администраторы также могут создавать особые параметры на уровне сайта.</span><span class="sxs-lookup"><span data-stu-id="9cc1e-108">Administrators also have the option of creating custom settings at the site scope.</span></span> <span data-ttu-id="9cc1e-109">При использовании эти параметров уровня сайта имеют приоритет над глобальными параметрами.</span><span class="sxs-lookup"><span data-stu-id="9cc1e-109">Whenever these site-scoped settings are used, they take precedence over the global settings.</span></span> <span data-ttu-id="9cc1e-110">Например, если созданы параметры уровня сайта для сайта Redmond, именно эти, а не глобальные параметры будут использоваться для управления качеством взаимодействия в сайте Redmond.</span><span class="sxs-lookup"><span data-stu-id="9cc1e-110">For example, if you create site-scoped settings for the Redmond site then those settings (rather than the global settings) will be used to manage QoE in Redmond.</span></span>
  
<span data-ttu-id="9cc1e-111">Параметры конфигурации качества взаимодействия можно создать с помощью любого из Скайп для панели управления Business Server или командлета [New-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csqoeconfiguration?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="9cc1e-111">QoE configuration settings can be created by using either Skype for Business Server Control Panel or the [New-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csqoeconfiguration?view=skype-ps) cmdlet.</span></span> <span data-ttu-id="9cc1e-112">При использовании Скайп для панели управления Business Server для создания новых параметров будут доступны для вас следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="9cc1e-112">If you are using Skype for Business Server Control Panel to create new settings the following options will be available to you:</span></span>
  
|<span data-ttu-id="9cc1e-113">**Параметр пользовательского интерфейса**</span><span class="sxs-lookup"><span data-stu-id="9cc1e-113">**UI setting**</span></span>|<span data-ttu-id="9cc1e-114">**Параметр PowerShell**</span><span class="sxs-lookup"><span data-stu-id="9cc1e-114">**PowerShell parameter**</span></span>|<span data-ttu-id="9cc1e-115">**Описание**</span><span class="sxs-lookup"><span data-stu-id="9cc1e-115">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="9cc1e-116">Имя</span><span class="sxs-lookup"><span data-stu-id="9cc1e-116">Name</span></span>  <br/> |<span data-ttu-id="9cc1e-117">Identity</span><span class="sxs-lookup"><span data-stu-id="9cc1e-117">Identity</span></span>  <br/> |<span data-ttu-id="9cc1e-p104">Уникальный идентификатор создаваемых параметров. Параметры конфигурации качества взаимодействия могут быть созданы только на уровне сайта.</span><span class="sxs-lookup"><span data-stu-id="9cc1e-p104">Unique identifier for the settings to be created. QoE configuration settings can only be created at the site scope.</span></span>  <br/> |
|<span data-ttu-id="9cc1e-120">Разрешить отслеживание данных о качестве связи</span><span class="sxs-lookup"><span data-stu-id="9cc1e-120">Enable monitoring of QoE data</span></span>  <br/> |<span data-ttu-id="9cc1e-121">EnableQoE</span><span class="sxs-lookup"><span data-stu-id="9cc1e-121">EnableQoE</span></span>  <br/> |<span data-ttu-id="9cc1e-122">Указывает, будут ли записи качества взаимодействия собраны и сохранены в базу данных мониторинга.</span><span class="sxs-lookup"><span data-stu-id="9cc1e-122">Specifies whether QoE records will be collected and saved to the monitoring database.</span></span>  <br/> |
|<span data-ttu-id="9cc1e-123">Разрешить очистку данных о качестве связи</span><span class="sxs-lookup"><span data-stu-id="9cc1e-123">Enable purging of QoE data</span></span>  <br/> |<span data-ttu-id="9cc1e-124">EnablePurging</span><span class="sxs-lookup"><span data-stu-id="9cc1e-124">EnablePurging</span></span>  <br/> |<span data-ttu-id="9cc1e-125">Определяет, можно ли очищать записи после истечения периода времени, определенного в свойстве **Хранить данные о качестве взаимодействия не дольше (дн.)**.</span><span class="sxs-lookup"><span data-stu-id="9cc1e-125">Specifies whether records will be purged after the duration defined in the **Keep QoE data for a maximum duration (days)** property has elapsed.</span></span> <br/> |
|<span data-ttu-id="9cc1e-126">Хранить данные о качестве взаимодействия не дольше (дн.):</span><span class="sxs-lookup"><span data-stu-id="9cc1e-126">Keep QoE data for maximum duration (days)</span></span>  <br/> |<span data-ttu-id="9cc1e-127">KeepQoEDataForDays</span><span class="sxs-lookup"><span data-stu-id="9cc1e-127">KeepQoEDataForDays</span></span>  <br/> |<span data-ttu-id="9cc1e-p105">Число дней хранения данных о качестве взаимодействия до удаления из базы данных. Это значение игнорируется, если очистка отключена.</span><span class="sxs-lookup"><span data-stu-id="9cc1e-p105">Number of days QoE data will be stored before being purged from the database. This value is ignored if purging is disabled.</span></span>  <br/> |
   
> [!NOTE]
> <span data-ttu-id="9cc1e-130">Командлет New-CsQoEConfiguration включает в себя дополнительные параметры недоступны в Скайп для панели управления Business Server.</span><span class="sxs-lookup"><span data-stu-id="9cc1e-130">The New-CsQoEConfiguration cmdlet includes additional options not available in Skype for Business Server Control Panel.</span></span> <span data-ttu-id="9cc1e-131">Для получения дополнительных сведений обратитесь к разделу справки [Командлета New-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csqoeconfiguration?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="9cc1e-131">For more information, see the [New-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csqoeconfiguration?view=skype-ps) help topic.</span></span>
  
### <a name="to-create-qoe-configuration-settings-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="9cc1e-132">Создание параметров конфигурации качества взаимодействия с помощью Скайп для панели управления Business Server</span><span class="sxs-lookup"><span data-stu-id="9cc1e-132">To create QoE configuration settings by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="9cc1e-p107">Войдите на компьютер как член группы RTCUniversalServerAdmins или роли CsVoiceAdministrator, CsServerAdministrator или CsAdministrator. Дополнительные сведения см. в разделе **Delegate Setup Permissions**.</span><span class="sxs-lookup"><span data-stu-id="9cc1e-p107">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role. For details, see **Delegate Setup Permissions**.</span></span>
    
2. <span data-ttu-id="9cc1e-135">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть Скайп для панели управления Business Server.</span><span class="sxs-lookup"><span data-stu-id="9cc1e-135">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="9cc1e-136">В левой панели навигации щелкните **Мониторинг и архивация** и затем выберите **Данные о качестве взаимодействия**.</span><span class="sxs-lookup"><span data-stu-id="9cc1e-136">In the left navigation bar, click **Monitoring and Archiving**, and then click **Quality of Experience Data**.</span></span>
    
4. <span data-ttu-id="9cc1e-137">На странице **Данные качества взаимодействия** нажмите кнопку **Создать**.</span><span class="sxs-lookup"><span data-stu-id="9cc1e-137">On the **Quality of Experience Data** page, click **New**.</span></span>
    
5. <span data-ttu-id="9cc1e-138">В разделе **Выбор сайта** щелкните сайт, к которому должна применяться эта политика, и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="9cc1e-138">In **Select a Site**, click the site to which the policy is to be applied, and click **OK**.</span></span>
    
6. <span data-ttu-id="9cc1e-139">На странице **Новый параметр качества обслуживания** сделайте следующее.</span><span class="sxs-lookup"><span data-stu-id="9cc1e-139">In **New Quality of Experience Setting**, do the following:</span></span>
    
   - <span data-ttu-id="9cc1e-140">Выберите пункт **Включить мониторинг данных качества обслуживания (CDR)**, чтобы включить мониторинг.</span><span class="sxs-lookup"><span data-stu-id="9cc1e-140">Select **Enable monitoring of QoE data** to turn on monitoring.</span></span>
    
   - <span data-ttu-id="9cc1e-141">Выберите пункт **Включить очистку данных качества обслуживания (CDR)**.</span><span class="sxs-lookup"><span data-stu-id="9cc1e-141">Select **Enable purging of QoE data** to turn on purging.</span></span>
    
   - <span data-ttu-id="9cc1e-142">В поле **Хранить записи сведений о звонках в течение (дней)** выберите максимальное количество дней, в течение которого должны храниться записи сведений о звонках.</span><span class="sxs-lookup"><span data-stu-id="9cc1e-142">In **Keep QoE for maximum duration (days)**, select the maximum number of days that QoE records should be retained.</span></span>
    
7. <span data-ttu-id="9cc1e-143">Нажмите **Исполнить**.</span><span class="sxs-lookup"><span data-stu-id="9cc1e-143">Click **Commit**.</span></span>
    
## <a name="creating-qoe-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="9cc1e-144">Создание параметров конфигурации качества взаимодействия с помощью командлетов Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="9cc1e-144">Creating QoE Configuration Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="9cc1e-145">Можно создать параметры конфигурации качества взаимодействия с помощью Windows PowerShell и командлет New-CsQoEConfiguration.</span><span class="sxs-lookup"><span data-stu-id="9cc1e-145">You can create QoE configuration settings by using Windows PowerShell and the New-CsQoEConfiguration cmdlet.</span></span> <span data-ttu-id="9cc1e-146">Можно выполнить этот командлет из Скайп для консоли Business Server или из удаленного сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9cc1e-146">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="9cc1e-147">Для получения дополнительных сведений об использовании удаленной оболочки Windows PowerShell для подключения к Скайп для Business Server в статье блога [«Быстрый запуск: управление Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell»](https://go.microsoft.com/fwlink/p/?linkId=255876).</span><span class="sxs-lookup"><span data-stu-id="9cc1e-147">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="9cc1e-148">Процесс одинаков в Скайп для Business Server.</span><span class="sxs-lookup"><span data-stu-id="9cc1e-148">The process is the same in Skype for Business Server.</span></span>
  
### <a name="to-create-a-new-collection-of-qoe-configuration-settings"></a><span data-ttu-id="9cc1e-149">Чтобы создать новую коллекцию параметров конфигурации качества взаимодействия</span><span class="sxs-lookup"><span data-stu-id="9cc1e-149">To create a new collection of QoE configuration settings</span></span>

 <span data-ttu-id="9cc1e-150">Эта команда создает новую коллекцию параметров конфигурации качества взаимодействия, применяемую на сайте Redmond:</span><span class="sxs-lookup"><span data-stu-id="9cc1e-150">This command creates a new collection of QoE configuration settings applied to the Redmond site:</span></span>
    
  ```
  New-CsQoEConfiguration -Identity "site:Redmond"
  ```

### <a name="to-create-a-new-collection-of-qoe-configuration-settings-where-qoe-monitoring-is-disabled"></a><span data-ttu-id="9cc1e-151">Чтобы создать новую коллекцию параметров конфигурации качества взаимодействия при отключенном мониторинге качества взаимодействия</span><span class="sxs-lookup"><span data-stu-id="9cc1e-151">To create a new collection of QoE configuration settings where QoE monitoring is disabled</span></span>

 <span data-ttu-id="9cc1e-p109">Так как никакие параметры (кроме обязательного параметра Identity) не были указаны в приведенных ранее командах, новая коллекция параметров конфигурации будет использовать значения по умолчанию для всех своих свойств. Чтобы создать параметры, использующие другие значения свойств просто включите соответствующий параметр и его значение. Например, чтобы создать коллекцию параметров конфигурации качества взаимодействия, которые, по умолчанию, разрешают отключать запись качества взаимодействия, используйте следующую команду:</span><span class="sxs-lookup"><span data-stu-id="9cc1e-p109">Because no parameters (other than the mandatory Identity parameter) were specified in the preceding command, the new collection of configuration settings will use the default values for all its properties. To create settings that use different property values, simply include the appropriate parameter and parameter value. For example, to create a collection of Quality of Experience configuration settings that, by default, allow disable QoE recording use a command like this:</span></span>
    
  ```
  New-CsQoEConfiguration -Identity "site:Redmond" -EnableQoE $False
  ```

### <a name="to-specify-multiple-property-values-when-creating-a-new-collection-of-qoe-configuration-settings"></a><span data-ttu-id="9cc1e-155">Чтобы указать значения нескольких свойств при создании новой коллекции параметров конфигурации качества взаимодействия</span><span class="sxs-lookup"><span data-stu-id="9cc1e-155">To specify multiple property values when creating a new collection of QoE configuration settings</span></span>

 <span data-ttu-id="9cc1e-p110">Можно задать несколько значений свойств, включив несколько параметров. Например, эта команда настраивает новые параметры для сохранения данных качества взаимодействия в течение 30 дней и очистки старых данных в 3:00:</span><span class="sxs-lookup"><span data-stu-id="9cc1e-p110">You can multiple property values by including multiple parameters. For example, this command configures the new settings to keep QoE data for 30 days and to purge old data at 3:00 AM:</span></span>
    
  ```
  New-CsQoEConfiguration -Identity "site:Redmond" -KeepQoEDataForDays 30 -PurgeHourOfDay 3
  ```

<span data-ttu-id="9cc1e-158">Для получения дополнительных сведений см раздел справки для командлета [New-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csqoeconfiguration?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="9cc1e-158">For more information, see the help topic for the [New-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csqoeconfiguration?view=skype-ps) cmdlet.</span></span>
  

