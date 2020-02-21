---
title: 'Lync Server 2013: Настройка объявлений для неназначенных номеров'
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
ms.openlocfilehash: 89f8fe84e046f49304d987fa51adf6dda61b8ce3
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42188582"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-announcements-for-unassigned-numbers-in-lync-server-2013"></a><span data-ttu-id="0682a-102">Настройка объявлений для неназначенных номеров в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0682a-102">Configuring announcements for unassigned numbers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0682a-103">_**Последнее изменение темы:** 2012-09-11_</span><span class="sxs-lookup"><span data-stu-id="0682a-103">_**Topic Last Modified:** 2012-09-11_</span></span>

<span data-ttu-id="0682a-104">Приложение извещения является функцией корпоративной голосовой связи, которая позволяет настраивать действия, выполняемые при вызове неназначенных расширений (расширения, допустимые для Организации, но не назначенные пользователю или телефону).</span><span class="sxs-lookup"><span data-stu-id="0682a-104">The Announcement application is an Enterprise Voice feature that enables you to configure what happens to calls to unassigned extensions (extensions that are valid for your organization, but are not assigned to a person or a phone).</span></span> <span data-ttu-id="0682a-105">Например, можно настроить эту функцию таким образом, чтобы при выполнении вызовов на неприсвоенные номера воспроизводилось сообщение и/или эти вызовы передавались на другое назначение.</span><span class="sxs-lookup"><span data-stu-id="0682a-105">For example, you can configure calls to unassigned numbers to play a message, or to be transferred to a different destination, or both.</span></span>

<span data-ttu-id="0682a-106">Приложение извещения устанавливается как компонент приложения группы ответа на сервере переднего плана или сервере Standard Edition при развертывании корпоративной голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="0682a-106">The Announcement application is installed as a feature of Response Group application on the Front End Server or Standard Edition server when you deploy Enterprise Voice.</span></span> <span data-ttu-id="0682a-107">Для настройки оповещений следует загрузить аудиофайлы или настроить преобразование текста в речь и сконфигурировать таблицу неприсвоенных номеров.</span><span class="sxs-lookup"><span data-stu-id="0682a-107">You need to configure Announcements by uploading your audio files or by configuring text-to-speech (TTS) and configuring the unassigned number table.</span></span>

<span data-ttu-id="0682a-108">В этом разделе описывается настройка объявлений Lync Server.</span><span class="sxs-lookup"><span data-stu-id="0682a-108">This section guides you through the configuration of Lync Server Announcements.</span></span> <span data-ttu-id="0682a-109">Предполагается, что вы уже прочитали разделы планирования, связанные с объявлениями и развернули сервер Enterprise Edition или сервер Standard Edition с корпоративной голосовой связью.</span><span class="sxs-lookup"><span data-stu-id="0682a-109">It assumes that you have already read the planning sections related to Announcements and deployed an Enterprise Edition server or a Standard Edition server with Enterprise Voice.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="0682a-110">Содержание</span><span class="sxs-lookup"><span data-stu-id="0682a-110">In This Section</span></span>

  - [<span data-ttu-id="0682a-111">Необходимые условия и роли для настройки объявлений в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0682a-111">Announcement configuration prerequisites and roles in Lync Server 2013</span></span>](lync-server-2013-announcement-configuration-prerequisites-and-roles.md)

  - [<span data-ttu-id="0682a-112">Процесс развертывания приложения "объявление" в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0682a-112">Deployment process for the Announcement application in Lync Server 2013</span></span>](lync-server-2013-deployment-process-for-the-announcement-application.md)

  - [<span data-ttu-id="0682a-113">Создание извещения в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0682a-113">Create an announcement in Lync Server 2013</span></span>](lync-server-2013-create-an-announcement.md)

  - [<span data-ttu-id="0682a-114">Настройка таблицы неназначенных номеров в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0682a-114">Configure the unassigned number table in Lync Server 2013</span></span>](lync-server-2013-configure-the-unassigned-number-table.md)

  - [<span data-ttu-id="0682a-115">Необязательно Проверка развертывания объявлений в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0682a-115">(Optional) Verify Announcement deployment in Lync Server 2013</span></span>](lync-server-2013-optional-verify-announcement-deployment.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="0682a-116">См. также</span><span class="sxs-lookup"><span data-stu-id="0682a-116">See Also</span></span>


[<span data-ttu-id="0682a-117">Планирование функций управления звонками в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0682a-117">Planning for call management features in Lync Server 2013</span></span>](lync-server-2013-planning-for-call-management-features.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

