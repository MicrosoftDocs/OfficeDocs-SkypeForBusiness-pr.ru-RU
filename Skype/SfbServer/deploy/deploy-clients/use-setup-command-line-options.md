---
title: Использование параметров командной строки установки в Skype для бизнеса Server 2015
ms.author: chucked
author: chuckedmonson
manager: serdars
ms.date: 10/20/2017
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 99878c3c-ff31-48e2-8424-580d7b07a7bf
description: 'Сводка: Сведения об операциях командной строки Setup.exe в программе установки Office.'
ms.openlocfilehash: 0fa4f31750697f0bd0dbe87bbde025cbc7f530bd
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2018
---
# <a name="use-setup-command-line-options-in-skype-for-business-server-2015"></a><span data-ttu-id="ba6a2-103">Использование параметров командной строки установки в Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="ba6a2-103">Use Setup command-line options in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="ba6a2-104">**Сводка:** Узнайте об операциях командной строки Setup.exe в программе установки Office.</span><span class="sxs-lookup"><span data-stu-id="ba6a2-104">**Summary:** Learn about Setup.exe command line operations in Office setup.</span></span>
  
<span data-ttu-id="ba6a2-105">Командная строка программы установки используется для выполнения достаточно редких операций в процессе установки Office.</span><span class="sxs-lookup"><span data-stu-id="ba6a2-105">The Setup.exe command line is used for very few operations in Office setup.</span></span> <span data-ttu-id="ba6a2-106">Вместо использования параметров командной строки программы установки, обычно используется центр развертывания Office и файл Config.xml для настройки программы установки и компонентов продукта.</span><span class="sxs-lookup"><span data-stu-id="ba6a2-106">Instead of using the Setup command-line options, you'll typically use the Office Customization Tool and the Config.xml file for product setup and feature customization.</span></span>
  
<span data-ttu-id="ba6a2-107">Командная строка программы установки Office распознает параметры командной строки, описанные в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="ba6a2-107">The Office Setup.exe command line recognizes the command-line options described in the following table.</span></span>
  
<span data-ttu-id="ba6a2-108">**Параметры командной строки программы установки Office**</span><span class="sxs-lookup"><span data-stu-id="ba6a2-108">**Office Setup Command-Line Options**</span></span>

|<span data-ttu-id="ba6a2-109">**Параметр командной строки программы установки**</span><span class="sxs-lookup"><span data-stu-id="ba6a2-109">**Setup Command-Line Option**</span></span>|<span data-ttu-id="ba6a2-110">**Описание**</span><span class="sxs-lookup"><span data-stu-id="ba6a2-110">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="ba6a2-111">/admin</span><span class="sxs-lookup"><span data-stu-id="ba6a2-111">/admin</span></span>  <br/> |<span data-ttu-id="ba6a2-112">Запускает центр развертывания Office для создания файла настройки программы установки (файла MSP).</span><span class="sxs-lookup"><span data-stu-id="ba6a2-112">Runs the Office Customization Tool to create a Setup customization file (.msp file).</span></span>  <br/> |
|<span data-ttu-id="ba6a2-113">/adminfile [путь]</span><span class="sxs-lookup"><span data-stu-id="ba6a2-113">/adminfile [path]</span></span>  <br/> |<span data-ttu-id="ba6a2-p102">Применяет к установке указанный файл настройки программы установки. Можно указать путь к конкретному MSP-файлу настройки или к папке файлов настройки.</span><span class="sxs-lookup"><span data-stu-id="ba6a2-p102">Applies the specified Setup customization file to the installation. You can specify a path of a specific customization file (.msp file) or to the folder where you store customization files.</span></span>  <br/> |
|<span data-ttu-id="ba6a2-116">/config [путь]</span><span class="sxs-lookup"><span data-stu-id="ba6a2-116">/config [path]</span></span>  <br/> |<span data-ttu-id="ba6a2-117">Указывает файл Config.xml, который программа установки использует во время установки.</span><span class="sxs-lookup"><span data-stu-id="ba6a2-117">Specifies the Config.xml file that Setup uses during the installation.</span></span> <span data-ttu-id="ba6a2-118">Используйте параметр/config для указания файла Config.xml, настроенные для Скайп для установок бизнеса, например:`/config \\server\share\Skype15\Skype.WW\Config.xml`</span><span class="sxs-lookup"><span data-stu-id="ba6a2-118">Use the /config option to specify the Config.xml file you customized for Skype for Business installations, for example:  `/config \\server\share\Skype15\Skype.WW\Config.xml`</span></span> <br/> |
|<span data-ttu-id="ba6a2-119">/modify Skype</span><span class="sxs-lookup"><span data-stu-id="ba6a2-119">/modify Skype</span></span>  <br/> |<span data-ttu-id="ba6a2-120">Используется с модифицированным файлом Config.xml для запуска программы установки в режиме обслуживания и изменения существующей установки Office.</span><span class="sxs-lookup"><span data-stu-id="ba6a2-120">Used with a modified Config.xml file to run Setup in maintenance mode and make changes to an existing Office installation.</span></span> <span data-ttu-id="ba6a2-121">Например, можно использовать / modify параметр, чтобы добавить или удалить Скайп для функций бизнес.</span><span class="sxs-lookup"><span data-stu-id="ba6a2-121">For example, you can use the /modify option to add or remove Skype for Business features.</span></span>  <br/> |
|<span data-ttu-id="ba6a2-122">/repair Skype</span><span class="sxs-lookup"><span data-stu-id="ba6a2-122">/repair Skype</span></span>  <br/> |<span data-ttu-id="ba6a2-123">Запускает программу установки на компьютере пользователя для восстановления Скайп для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="ba6a2-123">Runs Setup from the user's computer to repair Skype for Business.</span></span>  <br/> |
|<span data-ttu-id="ba6a2-124">/uninstall Skype</span><span class="sxs-lookup"><span data-stu-id="ba6a2-124">/uninstall Skype</span></span>  <br/> |<span data-ttu-id="ba6a2-125">Запускает программу установки для удаления Скайп для бизнеса с компьютера пользователя.</span><span class="sxs-lookup"><span data-stu-id="ba6a2-125">Runs Setup to remove Skype for Business from the user's computer.</span></span>  <br/> |
   
<span data-ttu-id="ba6a2-126">Сведения об использовании параметров командной строки программы установки в разделе [https://go.microsoft.com/fwlink/p/?linkid=267515](https://go.microsoft.com/fwlink/p/?linkid=267515).</span><span class="sxs-lookup"><span data-stu-id="ba6a2-126">For details about using the setup command-line options, see [https://go.microsoft.com/fwlink/p/?linkid=267515](https://go.microsoft.com/fwlink/p/?linkid=267515).</span></span> 
  

