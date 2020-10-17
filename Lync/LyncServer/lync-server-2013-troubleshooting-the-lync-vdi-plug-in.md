---
title: 'Lync Server 2013: Устранение неполадок подключаемого модуля VDI для Lync'
description: 'Lync Server 2013: Устранение неполадок подключаемого модуля VDI для Lync.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Troubleshooting the Lync VDI plug-in
ms:assetid: 183c9449-b907-409c-b5ed-b02af3bd93ee
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204713(v=OCS.15)
ms:contentKeyID: 48183525
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3cd2c0e3c8a47225f00ce280706dea2287e4dc8b
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48548945"
---
# <a name="troubleshooting-the-lync-vdi-plug-in-in-lync-server-2013"></a><span data-ttu-id="dc731-103">Устранение неполадок подключаемого модуля VDI для Lync в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dc731-103">Troubleshooting the Lync VDI plug-in in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dc731-104">_**Последнее изменение темы:** 2012-10-10_</span><span class="sxs-lookup"><span data-stu-id="dc731-104">_**Topic Last Modified:** 2012-10-10_</span></span>

<div>

## <a name="troubleshooting-issues-with-installing-the-lync-vdi-plug-in-on-a-thin-client"></a><span data-ttu-id="dc731-105">Устранение неполадок, связанных с установкой подключаемого модуля VDI для Lync на тонком клиенте</span><span class="sxs-lookup"><span data-stu-id="dc731-105">Troubleshooting Issues with Installing the Lync VDI Plug-in on a Thin Client</span></span>

<span data-ttu-id="dc731-106">В случае возникновения неполадок при установке подключаемого модуля VDI на тонком клиенте проверьте следующее:</span><span class="sxs-lookup"><span data-stu-id="dc731-106">If there are issues with installing the VDI plug-in on a thin client, check the following:</span></span>

  - <span data-ttu-id="dc731-107">Убедитесь в наличии достаточного свободного пространства в папке, указанной в системных переменных TEMP и TMP.</span><span class="sxs-lookup"><span data-stu-id="dc731-107">Ensure that there is sufficient space in the folder that you specified in the TEMP and TMP system variables.</span></span>

  - <span data-ttu-id="dc731-p101">Убедитесь в том, что защита от записи отключена. Инструкции см. в документации, предоставленной производителем устройства.</span><span class="sxs-lookup"><span data-stu-id="dc731-p101">Ensure that write-protect is turned off. Refer to your device manufacturer’s documentation for instructions.</span></span>

</div>

<div>

## <a name="troubleshooting-issues-with-pairing"></a><span data-ttu-id="dc731-110">Диагностика неполадок сопряжения</span><span class="sxs-lookup"><span data-stu-id="dc731-110">Troubleshooting Issues with Pairing</span></span>

<span data-ttu-id="dc731-111">Если не удается выполнить сопряжение подключаемого модуля VDI, значок сопряжения в нижнем правом углу имеет вид буквы "Х" красного цвета (см. иллюстрацию):</span><span class="sxs-lookup"><span data-stu-id="dc731-111">When VDI plug-in pairing fails, the pairing icon in the lower right displays as a red “X” as shown:</span></span>

<span data-ttu-id="dc731-112">![Значок VDI для Lync, иллюстрирующий успешные операции связывания](images/JJ204948.303d618c-4bc8-41c4-8553-2475de0d395e(OCS.15).png "Значок VDI для Lync, иллюстрирующий успешные операции связывания")</span><span class="sxs-lookup"><span data-stu-id="dc731-112">![Lync VDI icon showing successful pairing](images/JJ204948.303d618c-4bc8-41c4-8553-2475de0d395e(OCS.15).png "Lync VDI icon showing successful pairing")</span></span>

<span data-ttu-id="dc731-113">Далее перечислены возможные причины сбоя и рекомендуемые меры по исправлению:</span><span class="sxs-lookup"><span data-stu-id="dc731-113">The following are possible reasons for failures and the corrective actions you can take.</span></span>

  - <span data-ttu-id="dc731-114">**Пользователем введены неправильные учетные данные при входе в систему.**</span><span class="sxs-lookup"><span data-stu-id="dc731-114">**The user entered incorrect credentials during sign-in.**</span></span>
    
    <span data-ttu-id="dc731-115">Пользователь должен выйти из Lync и повторно войти с правильными учетными данными.</span><span class="sxs-lookup"><span data-stu-id="dc731-115">The user should sign out of Lync and sign in again with the correct credentials.</span></span> <span data-ttu-id="dc731-116">В повторно открывшемся диалоговом окне отобразится уведомление об успешном сопряжении.</span><span class="sxs-lookup"><span data-stu-id="dc731-116">The pairing dialog box will reappear and show whether pairing is successful.</span></span>

  - <span data-ttu-id="dc731-117">**Запущен еще один экземпляр клиента удаленного рабочего стола.**</span><span class="sxs-lookup"><span data-stu-id="dc731-117">**Another instance of the remote desktop client is running.**</span></span>
    
    <span data-ttu-id="dc731-118">Если в Windows используется подключение к удаленному рабочему столу, пользователи должны выполнить следующие действия:</span><span class="sxs-lookup"><span data-stu-id="dc731-118">If they are using Remote Desktop Connection in Windows, users should do the following:</span></span>
    
    1.  <span data-ttu-id="dc731-119">Запустить диспетчер задач: нажмите **Alt+Ctrl+Delete** и выберите **Запустить диспетчер задач**.</span><span class="sxs-lookup"><span data-stu-id="dc731-119">Start Task Manager: Press **Alt+Ctrl+Delete**, and then click **Start Task Manager**.</span></span>
    
    2.  <span data-ttu-id="dc731-120">Перейдите на вкладку **Процессы** и проверьте все процессы с именем **mstsc.exe** в списке.</span><span class="sxs-lookup"><span data-stu-id="dc731-120">Click the **Processes** tab and look for all processes named **mstsc.exe** in the list.</span></span>
    
    3.  <span data-ttu-id="dc731-121">Выделите каждый из процессов **mstsc.exe** и нажмите **Завершить процесс**.</span><span class="sxs-lookup"><span data-stu-id="dc731-121">Highlight each **mstsc.exe** process and then click **End Process**.</span></span>
    
    4.  <span data-ttu-id="dc731-122">Запустите новый сеанс удаленного рабочего стола и повторите попытку подключения.</span><span class="sxs-lookup"><span data-stu-id="dc731-122">Start a new remote desktop session and try connecting again.</span></span>

  - <span data-ttu-id="dc731-123">**Не удалось установить необходимые файлы.**</span><span class="sxs-lookup"><span data-stu-id="dc731-123">**The necessary files did not install correctly.**</span></span>
    
    <span data-ttu-id="dc731-124">После установки подключаемого модуля на локальном компьютере в разделе C: \\ Program Files \\ Microsoft Office \\ Office15 (или соответствующей букве диска) должны присутствовать следующие файлы:</span><span class="sxs-lookup"><span data-stu-id="dc731-124">After the plug-in is installed on the local computer, the following files should be present under C:\\Program Files\\Microsoft Office\\Office15 (or the appropriate drive letter):</span></span>
    
      - <span data-ttu-id="dc731-125">LyncVdiPlugin.dll</span><span class="sxs-lookup"><span data-stu-id="dc731-125">LyncVdiPlugin.dll</span></span>
    
      - <span data-ttu-id="dc731-126">UcVdi.dll</span><span class="sxs-lookup"><span data-stu-id="dc731-126">UcVdi.dll</span></span>
    
    <span data-ttu-id="dc731-127">В случае возникновения проблем с сопряжением подключаемого модуля VDI убедитесь в наличии этих файлов на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="dc731-127">If there are any issues with VDI pairing, check to make sure that these files are present on the local computer.</span></span>

  - <span data-ttu-id="dc731-128">**Клиент Lync запущен на локальном компьютере.**</span><span class="sxs-lookup"><span data-stu-id="dc731-128">**The Lync client is running on the local computer.**</span></span>
    
    <span data-ttu-id="dc731-129">Чтобы использовать подключаемый модуль VDI Lync, клиент Lync не должен выполняться на локальном компьютере, иначе связывание завершится с ошибками.</span><span class="sxs-lookup"><span data-stu-id="dc731-129">To use the Lync VDI plugin, a Lync client must not be running on the local computer, otherwise pairing will fail.</span></span> <span data-ttu-id="dc731-130">Рекомендуется не устанавливать клиент Lync на локальный компьютер.</span><span class="sxs-lookup"><span data-stu-id="dc731-130">As a best practice, the user should not install a Lync client on the local computer.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

