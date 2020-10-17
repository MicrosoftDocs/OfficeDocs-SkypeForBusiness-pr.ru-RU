---
title: 'Lync Server 2013: Настройка объявлений для неназначенных номеров'
description: 'Lync Server 2013: Настройка объявлений для неназначенных номеров.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring announcements for unassigned numbers
ms:assetid: 45633dd3-78de-4934-867e-33969fc25368
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425944(v=OCS.15)
ms:contentKeyID: 48184035
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 16ab636f0c6157118a00d5e46521555086c5e520
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48570035"
---
# <a name="configuring-announcements-for-unassigned-numbers-in-lync-server-2013"></a><span data-ttu-id="4bb63-103">Настройка объявлений для неназначенных номеров в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4bb63-103">Configuring announcements for unassigned numbers in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4bb63-104">_**Последнее изменение темы:** 2012-09-11_</span><span class="sxs-lookup"><span data-stu-id="4bb63-104">_**Topic Last Modified:** 2012-09-11_</span></span>

<span data-ttu-id="4bb63-105">Приложение извещения является функцией корпоративной голосовой связи, которая позволяет настраивать действия, выполняемые при вызове неназначенных расширений (расширения, допустимые для Организации, но не назначенные пользователю или телефону).</span><span class="sxs-lookup"><span data-stu-id="4bb63-105">The Announcement application is an Enterprise Voice feature that enables you to configure what happens to calls to unassigned extensions (extensions that are valid for your organization, but are not assigned to a person or a phone).</span></span> <span data-ttu-id="4bb63-106">Например, можно настроить эту функцию таким образом, чтобы при выполнении вызовов на неприсвоенные номера воспроизводилось сообщение и/или эти вызовы передавались на другое назначение.</span><span class="sxs-lookup"><span data-stu-id="4bb63-106">For example, you can configure calls to unassigned numbers to play a message, or to be transferred to a different destination, or both.</span></span>

<span data-ttu-id="4bb63-107">Приложение извещения устанавливается как компонент приложения группы ответа на сервере переднего плана или сервере Standard Edition при развертывании корпоративной голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="4bb63-107">The Announcement application is installed as a feature of Response Group application on the Front End Server or Standard Edition server when you deploy Enterprise Voice.</span></span> <span data-ttu-id="4bb63-108">Для настройки оповещений следует загрузить аудиофайлы или настроить преобразование текста в речь и сконфигурировать таблицу неприсвоенных номеров.</span><span class="sxs-lookup"><span data-stu-id="4bb63-108">You need to configure Announcements by uploading your audio files or by configuring text-to-speech (TTS) and configuring the unassigned number table.</span></span>

<span data-ttu-id="4bb63-109">В этом разделе описывается настройка объявлений Lync Server.</span><span class="sxs-lookup"><span data-stu-id="4bb63-109">This section guides you through the configuration of Lync Server Announcements.</span></span> <span data-ttu-id="4bb63-110">Предполагается, что вы уже прочитали разделы планирования, связанные с объявлениями и развернули сервер Enterprise Edition или сервер Standard Edition с корпоративной голосовой связью.</span><span class="sxs-lookup"><span data-stu-id="4bb63-110">It assumes that you have already read the planning sections related to Announcements and deployed an Enterprise Edition server or a Standard Edition server with Enterprise Voice.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="4bb63-111">Содержание</span><span class="sxs-lookup"><span data-stu-id="4bb63-111">In This Section</span></span>

  - [<span data-ttu-id="4bb63-112">Необходимые условия и роли для настройки объявлений в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4bb63-112">Announcement configuration prerequisites and roles in Lync Server 2013</span></span>](lync-server-2013-announcement-configuration-prerequisites-and-roles.md)

  - [<span data-ttu-id="4bb63-113">Процесс развертывания приложения "объявление" в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4bb63-113">Deployment process for the Announcement application in Lync Server 2013</span></span>](lync-server-2013-deployment-process-for-the-announcement-application.md)

  - [<span data-ttu-id="4bb63-114">Создание извещения в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4bb63-114">Create an announcement in Lync Server 2013</span></span>](lync-server-2013-create-an-announcement.md)

  - [<span data-ttu-id="4bb63-115">Настройка таблицы неназначенных номеров в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4bb63-115">Configure the unassigned number table in Lync Server 2013</span></span>](lync-server-2013-configure-the-unassigned-number-table.md)

  - [<span data-ttu-id="4bb63-116">Необязательно Проверка развертывания объявлений в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4bb63-116">(Optional) Verify Announcement deployment in Lync Server 2013</span></span>](lync-server-2013-optional-verify-announcement-deployment.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="4bb63-117">См. также</span><span class="sxs-lookup"><span data-stu-id="4bb63-117">See Also</span></span>


[<span data-ttu-id="4bb63-118">Планирование функций управления звонками в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4bb63-118">Planning for call management features in Lync Server 2013</span></span>](lync-server-2013-planning-for-call-management-features.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

