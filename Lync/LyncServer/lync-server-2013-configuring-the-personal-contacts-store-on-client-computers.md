---
title: 'Lync Server 2013: Настройка хранилища личных контактов на клиентских компьютерах'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring the personal contacts store on client computers
ms:assetid: ec69a6cb-07f2-4057-9544-55035f83eeae
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721922(v=OCS.15)
ms:contentKeyID: 49733857
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 77e6e48593bb3dc7a11375b13346ad59b2f40c0e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41734629"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-the-personal-contacts-store-on-client-computers-for-lync-server-2013"></a><span data-ttu-id="fd8c0-102">Настройка хранилища личных контактов на клиентских компьютерах для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fd8c0-102">Configuring the personal contacts store on client computers for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fd8c0-103">_**Тема последнего изменения:** 2014-02-05_</span><span class="sxs-lookup"><span data-stu-id="fd8c0-103">_**Topic Last Modified:** 2014-02-05_</span></span>

<span data-ttu-id="fd8c0-104">При интеграции Microsoft Lync Server 2013 и Microsoft Exchange Server 2013 рекомендуется настроить хранилище персональных контактов на любом клиентском компьютере, работающем под управлением Microsoft Lync 2010.</span><span class="sxs-lookup"><span data-stu-id="fd8c0-104">If you are integrating Microsoft Lync Server 2013 and Microsoft Exchange Server 2013 then it is recommended that you configure the personal contact store on any client computers running Microsoft Lync 2010.</span></span> <span data-ttu-id="fd8c0-105">В частности, вы должны настроить Lync для использования Exchange в качестве личного хранилища контактов и, в то же время, убедиться, что пользователи не могут переопределять это решение.</span><span class="sxs-lookup"><span data-stu-id="fd8c0-105">In particular, you should configure Lync to use Exchange as the personal contact store, and, at the same time, ensure that users are not able to override that decision.</span></span> <span data-ttu-id="fd8c0-106">Это можно сделать, создав и настроив значение реестра на каждом клиентском компьютере.</span><span class="sxs-lookup"><span data-stu-id="fd8c0-106">This can be done by creating and configuring a Registry value on each client computer.</span></span>

<span data-ttu-id="fd8c0-107">Обратите внимание, что это не требуется на компьютерах с Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="fd8c0-107">Note that this is not required on computers running Lync 2013.</span></span>

<span data-ttu-id="fd8c0-108">Чтобы настроить данное значение на одном компьютере, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="fd8c0-108">To configure this value on a single computer, complete the following procedure:</span></span>

1.  <span data-ttu-id="fd8c0-109">На клиентском компьютере нажмите кнопку **Пуск** и выберите команду **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="fd8c0-109">On the client computer, click **Start** and then click **Run**.</span></span>

2.  <span data-ttu-id="fd8c0-110">В диалоговом окне **Выполнить** введите regedit, а затем нажмите ВВОД.</span><span class="sxs-lookup"><span data-stu-id="fd8c0-110">In the **Run** dialog box, type regedit and then press ENTER.</span></span>

3.  <span data-ttu-id="fd8c0-111">В редакторе реестра разверните узел **hKey\_локального\_компьютера**, разверните раздел **программы**, **а затем разверните**раздел **Microsoft**, а затем — **Communicator**.</span><span class="sxs-lookup"><span data-stu-id="fd8c0-111">In Registry Editor, expand **HKEY\_LOCAL\_MACHINE**, expand **Software**, expand **Policies**, expand **Microsoft**, and then expand **Communicator**.</span></span>

4.  <span data-ttu-id="fd8c0-112">Щелкните элемент **Communicator** правой кнопкой мыши, наведите указатель на пункт **Создать** и выберите пункт **Параметр DWORD (32-разрядный)**.</span><span class="sxs-lookup"><span data-stu-id="fd8c0-112">Right-click **Communicator**, point to **New**, and then click **DWORD (32-bit) Value**.</span></span>

5.  <span data-ttu-id="fd8c0-113">После создания параметра введите **PersonalContactStoreOverride** и нажмите клавишу ВВОД, чтобы переименовать параметр.</span><span class="sxs-lookup"><span data-stu-id="fd8c0-113">After the new value is created, type **PersonalContactStoreOverride** and then press ENTER to rename the value.</span></span>

6.  <span data-ttu-id="fd8c0-114">Убедитесь, что значение PersonalContactStoreOverride равно 0, а затем закройте редактор реестра.</span><span class="sxs-lookup"><span data-stu-id="fd8c0-114">Verify that the value of PersonalContactStoreOverride is set to 0 and then close Registry Editor.</span></span>

<span data-ttu-id="fd8c0-115">Если нужно внести это изменение на нескольких компьютерах, это можно сделать, создав пользовательский объект групповой политики.</span><span class="sxs-lookup"><span data-stu-id="fd8c0-115">If you need to make this same change on multiple computers you can do so by creating a custom Group Policy object.</span></span> <span data-ttu-id="fd8c0-116">Подробные сведения можно найти в документации по групповой политике [http://go.microsoft.com/fwlink/p/?LinkId=268543](http://go.microsoft.com/fwlink/p/?linkid=268543).</span><span class="sxs-lookup"><span data-stu-id="fd8c0-116">For details, see the Group Policy documentation at [http://go.microsoft.com/fwlink/p/?LinkId=268543](http://go.microsoft.com/fwlink/p/?linkid=268543).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

