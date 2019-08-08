---
title: Использование файла config. XML для выполнения задач установки в клиентах Skype для бизнеса
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: PhillipGarding
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0813184a-ab40-417c-b3a3-c2090766b831
description: Сводка. Сведения об использовании файла Config.xml для определения дополнительных инструкций по установке.
ms.openlocfilehash: 31ee6c663822c2dab59a21fe5ca80c71cb81abf8
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/07/2019
ms.locfileid: "36234826"
---
# <a name="use-configxml-to-perform-installation-tasks-in-skype-for-business-clients"></a><span data-ttu-id="d3213-103">Использование файла config. XML для выполнения задач установки в клиентах Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="d3213-103">Use Config.xml to perform installation tasks in Skype for Business clients</span></span>

<span data-ttu-id="d3213-104">**Сводка.** Сведения об использовании файла Config.xml для определения дополнительных инструкций по установке.</span><span class="sxs-lookup"><span data-stu-id="d3213-104">**Summary:** How to use the Config.xml file to specify additional installation instructions.</span></span>

<span data-ttu-id="d3213-p101">Хотя Центр развертывания Office является основным средством настраиваемой установки, администраторы могут использовать файл Config.xml, чтобы задать для установки дополнительные инструкции, недоступные в Центре развертывания Office. Следующие настройки выполнимы только с помощью файла Config.xml:</span><span class="sxs-lookup"><span data-stu-id="d3213-p101">Although the Office Customization Tool (OCT) is the primary tool for customization installation, administrators can use the Config.xml file to specify additional installation instructions that are not available in the OCT. The following customizations can only be made by using the Config.xml file:</span></span>

- <span data-ttu-id="d3213-107">задание пути для точки сетевой установки;</span><span class="sxs-lookup"><span data-stu-id="d3213-107">Specify the path of the network installation point.</span></span>

- <span data-ttu-id="d3213-108">выбор устанавливаемых продуктов;</span><span class="sxs-lookup"><span data-stu-id="d3213-108">Select the products to install.</span></span>

- <span data-ttu-id="d3213-109">настройка ведения журнала и местоположения файла настроек установки и обновлений ПО;</span><span class="sxs-lookup"><span data-stu-id="d3213-109">Configure logging and the location of the Setup customization file and software updates.</span></span>

- <span data-ttu-id="d3213-110">задание параметров установки, таких как имя пользователя;</span><span class="sxs-lookup"><span data-stu-id="d3213-110">Specify installation options, such as user name.</span></span>

- <span data-ttu-id="d3213-111">копирование локального источника установки на компьютер пользователя без установки Office;</span><span class="sxs-lookup"><span data-stu-id="d3213-111">Copy the local installation source (LIS) to the user's computer without installing Office.</span></span>

- <span data-ttu-id="d3213-112">добавление и удаления языков из установки.</span><span class="sxs-lookup"><span data-stu-id="d3213-112">Add or remove languages from the installation.</span></span>

<span data-ttu-id="d3213-113">Мы рекомендуем использовать файл config. XML для настройки автоматической установки Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="d3213-113">We recommend that you use the Config.xml file to configure Skype for Business silent installation.</span></span> 

<span data-ttu-id="d3213-114">По умолчанию файл config. XML, хранящийся в основной папке продукта (например, \ _продукт_. WW) направляет настройку для установки этого продукта.</span><span class="sxs-lookup"><span data-stu-id="d3213-114">By default, the Config.xml file that is stored in the core product folder (for example, \ _product_.WW) directs Setup to install that product.</span></span> <span data-ttu-id="d3213-115">Например, с помощью файла config. XML в следующей папке устанавливается Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="d3213-115">For example, the Config.xml file in the following folder installs Skype for Business:</span></span>

- <span data-ttu-id="d3213-116">\\server\share\Skype15\Skype.WW \Конфиг.ксмл</span><span class="sxs-lookup"><span data-stu-id="d3213-116">\\server\share\Skype15\Skype.WW \Config.xml</span></span>

<span data-ttu-id="d3213-117">Элементы config. XML, наиболее часто используемые для установки Skype для бизнеса, перечислены в таблице ниже.</span><span class="sxs-lookup"><span data-stu-id="d3213-117">The Config.xml elements most commonly used for Skype for Business installation are listed in the following table.</span></span>

<span data-ttu-id="d3213-118">**Элементы Config.xml**</span><span class="sxs-lookup"><span data-stu-id="d3213-118">**Config.xml elements**</span></span>


| <span data-ttu-id="d3213-119">**Элемент**</span><span class="sxs-lookup"><span data-stu-id="d3213-119">**Element**</span></span>              | <span data-ttu-id="d3213-120">**Описание**</span><span class="sxs-lookup"><span data-stu-id="d3213-120">**Description**</span></span>                                                                                                                                                                                                                                                                                         |
|:-------------------------|:--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="d3213-121">Configuration</span><span class="sxs-lookup"><span data-stu-id="d3213-121">Configuration</span></span>  <br/>     | <span data-ttu-id="d3213-p103">Элемент верхнего уровня (обязательный). Содержит атрибут Product, например: Product=Lync. (Это работает только для клиентов Skype для бизнеса.)</span><span class="sxs-lookup"><span data-stu-id="d3213-p103">Top-level element (required). Contains the Product attribute, for example: Product=Lync (This will work for Skype for Business clients)</span></span>  <br/>                                                                                                                                                          |
| <span data-ttu-id="d3213-124">OptionState</span><span class="sxs-lookup"><span data-stu-id="d3213-124">OptionState</span></span>  <br/>       | <span data-ttu-id="d3213-125">Определяет, как при установке будут обрабатываться компоненты конкретного продукта.</span><span class="sxs-lookup"><span data-stu-id="d3213-125">Specifies how specific product features are handled during installation.</span></span> <span data-ttu-id="d3213-126">Используйте указанные ниже атрибуты, чтобы предотвратить установку служб Business Connectivity Services, включая общие компоненты, мешающие работе с Outlook.</span><span class="sxs-lookup"><span data-stu-id="d3213-126">Use the following attributes to prevent installation of Business Connectivity Services, which includes shared components that interfere with Outlook:</span></span> <br/>  <span data-ttu-id="d3213-127">Id="LOBiMain"</span><span class="sxs-lookup"><span data-stu-id="d3213-127">Id="LOBiMain"</span></span> <br/>  <span data-ttu-id="d3213-128">State="Absent"</span><span class="sxs-lookup"><span data-stu-id="d3213-128">State="Absent"</span></span> <br/>  <span data-ttu-id="d3213-129">Children="Force"</span><span class="sxs-lookup"><span data-stu-id="d3213-129">Children="Force"</span></span> <br/> |
| <span data-ttu-id="d3213-130">Display</span><span class="sxs-lookup"><span data-stu-id="d3213-130">Display</span></span>  <br/>           | <span data-ttu-id="d3213-p105">Уровень пользовательского интерфейса, отображаемого пользователю программой установки. Обычно используются следующие атрибуты:</span><span class="sxs-lookup"><span data-stu-id="d3213-p105">The level of UI that Setup displays to the user. Typical attributes include the following:</span></span> <br/>  <span data-ttu-id="d3213-133">Комплетионнотице = "Да"</span><span class="sxs-lookup"><span data-stu-id="d3213-133">CompletionNotice="Yes"</span></span>                                                                                                                                                                                |
| <span data-ttu-id="d3213-134">Logging</span><span class="sxs-lookup"><span data-stu-id="d3213-134">Logging</span></span>  <br/>           | <span data-ttu-id="d3213-p106">Параметры ведения журнала программой установки. Обычно используются следующие атрибуты:</span><span class="sxs-lookup"><span data-stu-id="d3213-p106">Options for the kind of logging that Setup performs. Typical attributes include the following:</span></span> <br/>  <span data-ttu-id="d3213-137">Введите = "OFF"</span><span class="sxs-lookup"><span data-stu-id="d3213-137">Type ="Off"</span></span>                                                                                                                                                                                       |
| <span data-ttu-id="d3213-138">Setting</span><span class="sxs-lookup"><span data-stu-id="d3213-138">Setting</span></span>  <br/>           | <span data-ttu-id="d3213-p107">Определяет значения для свойств программы установщика Windows. Обычно используются следующие атрибуты:</span><span class="sxs-lookup"><span data-stu-id="d3213-p107">Specifies values for Windows Installer properties. Typical attributes include the following: </span></span><br/>  <span data-ttu-id="d3213-141">Параметр ID = " *имя*" (имя свойства установщика Windows)</span><span class="sxs-lookup"><span data-stu-id="d3213-141">Setting Id=" *name*" (the name of the Windows Installer property)</span></span>  <br/>  <span data-ttu-id="d3213-142">Value = " *value*" (значение, которое нужно присвоить свойству)</span><span class="sxs-lookup"><span data-stu-id="d3213-142">Value=" *value*" (the value to assign to the property)</span></span>  <br/>                                                             |
| <span data-ttu-id="d3213-143">DistributionPoint</span><span class="sxs-lookup"><span data-stu-id="d3213-143">DistributionPoint</span></span>  <br/> | <span data-ttu-id="d3213-p108">Полный доменный путь точки сетевой установки, из которой запускается установка. Содержит атрибут Location:</span><span class="sxs-lookup"><span data-stu-id="d3213-p108">The fully qualified path of the network installation point from which the installation is to run. Includes the Location attribute: </span></span><br/>  <span data-ttu-id="d3213-146">Location = " *путь*"</span><span class="sxs-lookup"><span data-stu-id="d3213-146">Location=" *path*"</span></span>  <br/>                                                                                                                                     |

<span data-ttu-id="d3213-147">В следующем примере показан файл config. XML для типичной автоматической установки клиента Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="d3213-147">The following example shows a Config.xml file for a typical silent installation of the Skype for Business client.</span></span> 

```
<Configuration Product="Lync"> 
  <OptionState Id="LOBiMain" State="Absent" Children="Force" /> 
  <Display Level="None" CompletionNotice="No" AcceptEula="Yes" /> 
  <Logging Type="verbose" Path="%temp%" Template="LyncSetupVerbose(*).log" />
  <Setting Id="SETUP_REBOOT" Value="Never" /> 
  <DistributionPoint Location="\\server\share\Skype15" /> 
</Configuration>
```

<span data-ttu-id="d3213-148">Подробные сведения об использовании файла config. XML для выполнения задач по установке и сопровождению Office можно найти [https://go.microsoft.com/fwlink/p/?linkid=267514](https://go.microsoft.com/fwlink/p/?linkid=267514)по адресу.</span><span class="sxs-lookup"><span data-stu-id="d3213-148">Detailed information about using the Config.xml file to perform Office installation and maintenance tasks is available at [https://go.microsoft.com/fwlink/p/?linkid=267514](https://go.microsoft.com/fwlink/p/?linkid=267514).</span></span>

## <a name="to-customize-the-configxml-file"></a><span data-ttu-id="d3213-149">Изменение файла Config.xml</span><span class="sxs-lookup"><span data-stu-id="d3213-149">To customize the Config.xml file</span></span>

1. <span data-ttu-id="d3213-150">Откройте файл Config.xml с помощью текстового редактора, такого как "Блокнот".</span><span class="sxs-lookup"><span data-stu-id="d3213-150">Open the Config.xml file by using a text editor tool, such as Notepad.</span></span>

2. <span data-ttu-id="d3213-151">Найдите строки, содержащие элементы, которые нужно изменить.</span><span class="sxs-lookup"><span data-stu-id="d3213-151">Locate the lines that contain the elements you want to change.</span></span>

3. <span data-ttu-id="d3213-152">Измените запись для элемента, используя нужные значения параметров автоматической установки.</span><span class="sxs-lookup"><span data-stu-id="d3213-152">Modify the element entry with the silent options that you want to use.</span></span> <span data-ttu-id="d3213-153">Убедитесь, что вы удалите разделители комментариев, "\<!--" и "--\>".</span><span class="sxs-lookup"><span data-stu-id="d3213-153">Make sure that you remove the comment delimiters, "\<!--" and "--\>".</span></span> <span data-ttu-id="d3213-154">Например, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="d3213-154">For example, use the following syntax:</span></span>

   <pre>
   < DistributionPoint Location="\\server\share\Skype15" />
   </pre>

4. <span data-ttu-id="d3213-155">Сохраните файл Config.xml.</span><span class="sxs-lookup"><span data-stu-id="d3213-155">Save the Config.xml file.</span></span>


