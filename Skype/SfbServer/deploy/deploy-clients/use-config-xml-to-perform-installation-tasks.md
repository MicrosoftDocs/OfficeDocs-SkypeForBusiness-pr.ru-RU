---
title: Использование файла Config.xml для выполнения задач установки в Скайп пользователей
ms.author: chucked
author: chuckedmonson
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0813184a-ab40-417c-b3a3-c2090766b831
description: Сводка. Сведения об использовании файла Config.xml для определения дополнительных инструкций по установке.
ms.openlocfilehash: ea869fe2b49d5c1a5b4e04c3bc75cfd52b66555e
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2018
ms.locfileid: "21003510"
---
# <a name="use-configxml-to-perform-installation-tasks-in-skype-for-business-clients"></a><span data-ttu-id="a41a1-103">Использование файла Config.xml для выполнения задач установки в Скайп пользователей</span><span class="sxs-lookup"><span data-stu-id="a41a1-103">Use Config.xml to perform installation tasks in Skype for Business clients</span></span>
 
<span data-ttu-id="a41a1-104">**Сводка.** Сведения об использовании файла Config.xml для определения дополнительных инструкций по установке.</span><span class="sxs-lookup"><span data-stu-id="a41a1-104">**Summary:** How to use the Config.xml file to specify additional installation instructions.</span></span>
  
<span data-ttu-id="a41a1-p101">Хотя Центр развертывания Office является основным средством настраиваемой установки, администраторы могут использовать файл Config.xml, чтобы задать для установки дополнительные инструкции, недоступные в Центре развертывания Office. Следующие настройки выполнимы только с помощью файла Config.xml:</span><span class="sxs-lookup"><span data-stu-id="a41a1-p101">Although the Office Customization Tool (OCT) is the primary tool for customization installation, administrators can use the Config.xml file to specify additional installation instructions that are not available in the OCT. The following customizations can only be made by using the Config.xml file:</span></span>
  
- <span data-ttu-id="a41a1-107">задание пути для точки сетевой установки;</span><span class="sxs-lookup"><span data-stu-id="a41a1-107">Specify the path of the network installation point.</span></span>
    
- <span data-ttu-id="a41a1-108">выбор устанавливаемых продуктов;</span><span class="sxs-lookup"><span data-stu-id="a41a1-108">Select the products to install.</span></span>
    
- <span data-ttu-id="a41a1-109">настройка ведения журнала и местоположения файла настроек установки и обновлений ПО;</span><span class="sxs-lookup"><span data-stu-id="a41a1-109">Configure logging and the location of the Setup customization file and software updates.</span></span>
    
- <span data-ttu-id="a41a1-110">задание параметров установки, таких как имя пользователя;</span><span class="sxs-lookup"><span data-stu-id="a41a1-110">Specify installation options, such as user name.</span></span>
    
- <span data-ttu-id="a41a1-111">копирование локального источника установки на компьютер пользователя без установки Office;</span><span class="sxs-lookup"><span data-stu-id="a41a1-111">Copy the local installation source (LIS) to the user's computer without installing Office.</span></span>
    
- <span data-ttu-id="a41a1-112">добавление и удаления языков из установки.</span><span class="sxs-lookup"><span data-stu-id="a41a1-112">Add or remove languages from the installation.</span></span>
    
<span data-ttu-id="a41a1-113">Мы рекомендуем использовать файл Config.xml для настройки Скайп для бизнеса автоматической установки.</span><span class="sxs-lookup"><span data-stu-id="a41a1-113">We recommend that you use the Config.xml file to configure Skype for Business silent installation.</span></span> 
  
<span data-ttu-id="a41a1-114">По умолчанию в файле Config.xml, который хранится в папке основного продукта (например, \ _продукта_. WW) направляет программы установки для установки продукта.</span><span class="sxs-lookup"><span data-stu-id="a41a1-114">By default, the Config.xml file that is stored in the core product folder (for example, \ _product_.WW) directs Setup to install that product.</span></span> <span data-ttu-id="a41a1-115">Например файл Config.xml в папке устанавливает Скайп для бизнеса:</span><span class="sxs-lookup"><span data-stu-id="a41a1-115">For example, the Config.xml file in the following folder installs Skype for Business:</span></span>
  
- <span data-ttu-id="a41a1-116">\\server\share\Skype15\Skype.ww \Config.xml</span><span class="sxs-lookup"><span data-stu-id="a41a1-116">\\server\share\Skype15\Skype.WW \Config.xml</span></span>
    
<span data-ttu-id="a41a1-117">В следующей таблице перечислены элементы Config.xml, чаще всего используемые для Скайп для установки Business.</span><span class="sxs-lookup"><span data-stu-id="a41a1-117">The Config.xml elements most commonly used for Skype for Business installation are listed in the following table.</span></span>
  
<span data-ttu-id="a41a1-118">**Элементы Config.xml**</span><span class="sxs-lookup"><span data-stu-id="a41a1-118">**Config.xml elements**</span></span>

|<span data-ttu-id="a41a1-119">**Элемент**</span><span class="sxs-lookup"><span data-stu-id="a41a1-119">**Element**</span></span>|<span data-ttu-id="a41a1-120">**Описание**</span><span class="sxs-lookup"><span data-stu-id="a41a1-120">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="a41a1-121">Configuration</span><span class="sxs-lookup"><span data-stu-id="a41a1-121">Configuration</span></span>  <br/> |<span data-ttu-id="a41a1-p103">Элемент верхнего уровня (обязательный). Содержит атрибут Product, например: Product=Lync. (Это работает только для клиентов Skype для бизнеса.)</span><span class="sxs-lookup"><span data-stu-id="a41a1-p103">Top-level element (required). Contains the Product attribute, for example: Product=Lync (This will work for Skype for Business clients)</span></span>  <br/> |
|<span data-ttu-id="a41a1-124">OptionState</span><span class="sxs-lookup"><span data-stu-id="a41a1-124">OptionState</span></span>  <br/> | <span data-ttu-id="a41a1-125">Определяет, как при установке будут обрабатываться компоненты конкретного продукта.</span><span class="sxs-lookup"><span data-stu-id="a41a1-125">Specifies how specific product features are handled during installation.</span></span> <span data-ttu-id="a41a1-126">Используйте следующие атрибуты для предотвращения установки служб Business Connectivity Services, который включает в себя общие компоненты, которые мешают Outlook:</span><span class="sxs-lookup"><span data-stu-id="a41a1-126">Use the following attributes to prevent installation of Business Connectivity Services, which includes shared components that interfere with Outlook:</span></span> <br/>  <span data-ttu-id="a41a1-127">ID = «LOBiMain»</span><span class="sxs-lookup"><span data-stu-id="a41a1-127">Id="LOBiMain"</span></span> <br/>  <span data-ttu-id="a41a1-128">State="Absent"</span><span class="sxs-lookup"><span data-stu-id="a41a1-128">State="Absent"</span></span> <br/>  <span data-ttu-id="a41a1-129">Children="Force"</span><span class="sxs-lookup"><span data-stu-id="a41a1-129">Children="Force"</span></span> <br/> |
|<span data-ttu-id="a41a1-130">Display</span><span class="sxs-lookup"><span data-stu-id="a41a1-130">Display</span></span>  <br/> | <span data-ttu-id="a41a1-p105">Уровень пользовательского интерфейса, отображаемого пользователю программой установки. Обычно используются следующие атрибуты:</span><span class="sxs-lookup"><span data-stu-id="a41a1-p105">The level of UI that Setup displays to the user. Typical attributes include the following:</span></span> <br/>  <span data-ttu-id="a41a1-133">CompletionNotice = «Yes»</span><span class="sxs-lookup"><span data-stu-id="a41a1-133">CompletionNotice="Yes"</span></span> | <span data-ttu-id="a41a1-134">No"(default) «</span><span class="sxs-lookup"><span data-stu-id="a41a1-134">"No"(default)</span></span> <br/>  <span data-ttu-id="a41a1-135">AcceptEula = «Yes»</span><span class="sxs-lookup"><span data-stu-id="a41a1-135">AcceptEula="Yes"</span></span> | <span data-ttu-id="a41a1-136">No"(default) «</span><span class="sxs-lookup"><span data-stu-id="a41a1-136">"No"(default)</span></span> <br/> |
|<span data-ttu-id="a41a1-137">Logging</span><span class="sxs-lookup"><span data-stu-id="a41a1-137">Logging</span></span>  <br/> | <span data-ttu-id="a41a1-p106">Параметры ведения журнала программой установки. Обычно используются следующие атрибуты:</span><span class="sxs-lookup"><span data-stu-id="a41a1-p106">Options for the kind of logging that Setup performs. Typical attributes include the following:</span></span> <br/>  <span data-ttu-id="a41a1-140">Тип = «Off»</span><span class="sxs-lookup"><span data-stu-id="a41a1-140">Type ="Off"</span></span> | <span data-ttu-id="a41a1-141">Standard"(default) «</span><span class="sxs-lookup"><span data-stu-id="a41a1-141">"Standard"(default)</span></span> | <span data-ttu-id="a41a1-142">«Verbose»</span><span class="sxs-lookup"><span data-stu-id="a41a1-142">"Verbose"</span></span> <br/>  <span data-ttu-id="a41a1-143">Шаблон =» _filename_.txt» (имя файла журнала)</span><span class="sxs-lookup"><span data-stu-id="a41a1-143">Template=" _filename_.txt" (the name of the log file)</span></span>  <br/> |
|<span data-ttu-id="a41a1-144">Setting</span><span class="sxs-lookup"><span data-stu-id="a41a1-144">Setting</span></span>  <br/> | <span data-ttu-id="a41a1-p107">Определяет значения для свойств программы установщика Windows. Обычно используются следующие атрибуты:</span><span class="sxs-lookup"><span data-stu-id="a41a1-p107">Specifies values for Windows Installer properties. Typical attributes include the following: </span></span><br/>  <span data-ttu-id="a41a1-147">Setting Id =» _имя_"(имя свойства установщика Windows)</span><span class="sxs-lookup"><span data-stu-id="a41a1-147">Setting Id=" _name_" (the name of the Windows Installer property)</span></span>  <br/>  <span data-ttu-id="a41a1-148">Значение =» _значение_"(значение, задаваемое свойству)</span><span class="sxs-lookup"><span data-stu-id="a41a1-148">Value=" _value_" (the value to assign to the property)</span></span>  <br/> |
|<span data-ttu-id="a41a1-149">DistributionPoint</span><span class="sxs-lookup"><span data-stu-id="a41a1-149">DistributionPoint</span></span>  <br/> | <span data-ttu-id="a41a1-p108">Полный доменный путь точки сетевой установки, из которой запускается установка. Содержит атрибут Location:</span><span class="sxs-lookup"><span data-stu-id="a41a1-p108">The fully qualified path of the network installation point from which the installation is to run. Includes the Location attribute: </span></span><br/>  <span data-ttu-id="a41a1-152">Расположение =» _путь_"</span><span class="sxs-lookup"><span data-stu-id="a41a1-152">Location=" _path_"</span></span>  <br/> |
   
<span data-ttu-id="a41a1-153">Следующий пример показывает файл Config.xml для типичной автоматической установки Скайп для клиента Business.</span><span class="sxs-lookup"><span data-stu-id="a41a1-153">The following example shows a Config.xml file for a typical silent installation of the Skype for Business client.</span></span> 
  
```
<Configuration Product="Lync"> 
  <OptionState Id="LOBiMain" State="Absent" Children="Force" /> 
  <Display Level="None" CompletionNotice="No" AcceptEula="Yes" /> 
  <Logging Type="verbose" Path="%temp%" Template="LyncSetupVerbose(*).log" />
  <Setting Id="SETUP_REBOOT" Value="Never" /> 
  <DistributionPoint Location="\\server\share\Skype15" /> 
</Configuration>
```

<span data-ttu-id="a41a1-154">Подробные сведения об использовании файла Config.xml для выполнения задач установки и обслуживания Office доступном по адресу [https://go.microsoft.com/fwlink/p/?linkid=267514](https://go.microsoft.com/fwlink/p/?linkid=267514).</span><span class="sxs-lookup"><span data-stu-id="a41a1-154">Detailed information about using the Config.xml file to perform Office installation and maintenance tasks is available at [https://go.microsoft.com/fwlink/p/?linkid=267514](https://go.microsoft.com/fwlink/p/?linkid=267514).</span></span>
  
## <a name="to-customize-the-configxml-file"></a><span data-ttu-id="a41a1-155">Изменение файла Config.xml</span><span class="sxs-lookup"><span data-stu-id="a41a1-155">To customize the Config.xml file</span></span>

1. <span data-ttu-id="a41a1-156">Откройте файл Config.xml с помощью текстового редактора, такого как "Блокнот".</span><span class="sxs-lookup"><span data-stu-id="a41a1-156">Open the Config.xml file by using a text editor tool, such as Notepad.</span></span>
    
2. <span data-ttu-id="a41a1-157">Найдите строки, содержащие элементы, которые нужно изменить.</span><span class="sxs-lookup"><span data-stu-id="a41a1-157">Locate the lines that contain the elements you want to change.</span></span>
    
3. <span data-ttu-id="a41a1-158">Измените запись для элемента, используя нужные значения параметров автоматической установки.</span><span class="sxs-lookup"><span data-stu-id="a41a1-158">Modify the element entry with the silent options that you want to use.</span></span> <span data-ttu-id="a41a1-159">Убедитесь в том, что вы удалить разделители комментариев "\<!--» и «--\>«.</span><span class="sxs-lookup"><span data-stu-id="a41a1-159">Make sure that you remove the comment delimiters, "\<!--" and "--\>".</span></span> <span data-ttu-id="a41a1-160">Например, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="a41a1-160">For example, use the following syntax:</span></span>
    
  <pre>
  < DistributionPoint Location="\\server\share\Skype15" />
  </pre>

4. <span data-ttu-id="a41a1-161">Сохраните файл Config.xml.</span><span class="sxs-lookup"><span data-stu-id="a41a1-161">Save the Config.xml file.</span></span>
    

