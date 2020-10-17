---
title: 'Lync Server 2013: Настройка хранилища личных контактов на клиентских компьютерах'
description: 'Lync Server 2013: Настройка хранилища личных контактов на клиентских компьютерах.'
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
ms.openlocfilehash: c1040b3eb9aa38e3e0c537d690b9292ab8f1ead2
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48544195"
---
# <a name="configuring-the-personal-contacts-store-on-client-computers-for-lync-server-2013"></a><span data-ttu-id="74fee-103">Настройка хранилища личных контактов на клиентских компьютерах для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="74fee-103">Configuring the personal contacts store on client computers for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="74fee-104">_**Последнее изменение темы:** 2014-02-05_</span><span class="sxs-lookup"><span data-stu-id="74fee-104">_**Topic Last Modified:** 2014-02-05_</span></span>

<span data-ttu-id="74fee-105">При интеграции Microsoft Lync Server 2013 и Microsoft Exchange Server 2013 рекомендуется настроить хранилище личных контактов на всех клиентских компьютерах, работающих под управлением Microsoft Lync 2010.</span><span class="sxs-lookup"><span data-stu-id="74fee-105">If you are integrating Microsoft Lync Server 2013 and Microsoft Exchange Server 2013 then it is recommended that you configure the personal contact store on any client computers running Microsoft Lync 2010.</span></span> <span data-ttu-id="74fee-106">В частности, необходимо настроить Lync для использования Exchange в качестве личного хранилища контактов и, в то же время, убедиться, что пользователи не могут переопределить это решение.</span><span class="sxs-lookup"><span data-stu-id="74fee-106">In particular, you should configure Lync to use Exchange as the personal contact store, and, at the same time, ensure that users are not able to override that decision.</span></span> <span data-ttu-id="74fee-107">Это можно сделать, создав и настроив значение реестра на каждом клиентском компьютере.</span><span class="sxs-lookup"><span data-stu-id="74fee-107">This can be done by creating and configuring a Registry value on each client computer.</span></span>

<span data-ttu-id="74fee-108">Обратите внимание, что это не обязательно на компьютерах с Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="74fee-108">Note that this is not required on computers running Lync 2013.</span></span>

<span data-ttu-id="74fee-109">Чтобы настроить данное значение на одном компьютере, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="74fee-109">To configure this value on a single computer, complete the following procedure:</span></span>

1.  <span data-ttu-id="74fee-110">На клиентском компьютере нажмите кнопку **Пуск** и выберите команду **выполнить**.</span><span class="sxs-lookup"><span data-stu-id="74fee-110">On the client computer, click **Start** and then click **Run**.</span></span>

2.  <span data-ttu-id="74fee-111">В диалоговом окне **Выполнить** введите regedit, затем нажмите ВВОД.</span><span class="sxs-lookup"><span data-stu-id="74fee-111">In the **Run** dialog box, type regedit and then press ENTER.</span></span>

3.  <span data-ttu-id="74fee-112">В редакторе реестра разверните узел **" \_ локальный \_ компьютер**", разверните узел **программное обеспечение**, **политики**, разверните узел **Microsoft**, а затем — **Communicator**.</span><span class="sxs-lookup"><span data-stu-id="74fee-112">In Registry Editor, expand **HKEY\_LOCAL\_MACHINE**, expand **Software**, expand **Policies**, expand **Microsoft**, and then expand **Communicator**.</span></span>

4.  <span data-ttu-id="74fee-113">Щелкните правой кнопкой мыши **Communicator**, наведите указатель мыши на **создать**и выберите **значение DWORD (32-бит)**.</span><span class="sxs-lookup"><span data-stu-id="74fee-113">Right-click **Communicator**, point to **New**, and then click **DWORD (32-bit) Value**.</span></span>

5.  <span data-ttu-id="74fee-114">После создания нового значения введите **PersonalContactStoreOverride** и нажмите КЛАВИШу ввод, чтобы переименовать значение.</span><span class="sxs-lookup"><span data-stu-id="74fee-114">After the new value is created, type **PersonalContactStoreOverride** and then press ENTER to rename the value.</span></span>

6.  <span data-ttu-id="74fee-115">Убедитесь, что значение PersonalContactStoreOverride равно 0, а затем закройте редактор реестра.</span><span class="sxs-lookup"><span data-stu-id="74fee-115">Verify that the value of PersonalContactStoreOverride is set to 0 and then close Registry Editor.</span></span>

<span data-ttu-id="74fee-116">Если нужно внести это изменение на нескольких компьютерах, это можно сделать, создав пользовательский объект групповой политики.</span><span class="sxs-lookup"><span data-stu-id="74fee-116">If you need to make this same change on multiple computers you can do so by creating a custom Group Policy object.</span></span> <span data-ttu-id="74fee-117">Дополнительные сведения см. в документации по групповой политике [https://go.microsoft.com/fwlink/p/?LinkId=268543](https://go.microsoft.com/fwlink/p/?linkid=268543) .</span><span class="sxs-lookup"><span data-stu-id="74fee-117">For details, see the Group Policy documentation at [https://go.microsoft.com/fwlink/p/?LinkId=268543](https://go.microsoft.com/fwlink/p/?linkid=268543).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

