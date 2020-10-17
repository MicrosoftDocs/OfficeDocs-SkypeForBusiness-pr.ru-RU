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
ms.openlocfilehash: c352e7a4f062e6a9a1aab0bf52289c20102cc7fe
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48517556"
---
# <a name="configuring-announcements-for-unassigned-numbers-in-lync-server-2013"></a><span data-ttu-id="84fd6-102">Настройка объявлений для неназначенных номеров в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="84fd6-102">Configuring announcements for unassigned numbers in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="84fd6-103">_**Последнее изменение темы:** 2012-09-11_</span><span class="sxs-lookup"><span data-stu-id="84fd6-103">_**Topic Last Modified:** 2012-09-11_</span></span>

<span data-ttu-id="84fd6-104">Приложение извещения является функцией корпоративной голосовой связи, которая позволяет настраивать действия, выполняемые при вызове неназначенных расширений (расширения, допустимые для Организации, но не назначенные пользователю или телефону).</span><span class="sxs-lookup"><span data-stu-id="84fd6-104">The Announcement application is an Enterprise Voice feature that enables you to configure what happens to calls to unassigned extensions (extensions that are valid for your organization, but are not assigned to a person or a phone).</span></span> <span data-ttu-id="84fd6-105">Например, можно настроить эту функцию таким образом, чтобы при выполнении вызовов на неприсвоенные номера воспроизводилось сообщение и/или эти вызовы передавались на другое назначение.</span><span class="sxs-lookup"><span data-stu-id="84fd6-105">For example, you can configure calls to unassigned numbers to play a message, or to be transferred to a different destination, or both.</span></span>

<span data-ttu-id="84fd6-106">Приложение извещения устанавливается как компонент приложения группы ответа на сервере переднего плана или сервере Standard Edition при развертывании корпоративной голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="84fd6-106">The Announcement application is installed as a feature of Response Group application on the Front End Server or Standard Edition server when you deploy Enterprise Voice.</span></span> <span data-ttu-id="84fd6-107">Для настройки оповещений следует загрузить аудиофайлы или настроить преобразование текста в речь и сконфигурировать таблицу неприсвоенных номеров.</span><span class="sxs-lookup"><span data-stu-id="84fd6-107">You need to configure Announcements by uploading your audio files or by configuring text-to-speech (TTS) and configuring the unassigned number table.</span></span>

<span data-ttu-id="84fd6-108">В этом разделе описывается настройка объявлений Lync Server.</span><span class="sxs-lookup"><span data-stu-id="84fd6-108">This section guides you through the configuration of Lync Server Announcements.</span></span> <span data-ttu-id="84fd6-109">Предполагается, что вы уже прочитали разделы планирования, связанные с объявлениями и развернули сервер Enterprise Edition или сервер Standard Edition с корпоративной голосовой связью.</span><span class="sxs-lookup"><span data-stu-id="84fd6-109">It assumes that you have already read the planning sections related to Announcements and deployed an Enterprise Edition server or a Standard Edition server with Enterprise Voice.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="84fd6-110">Содержание</span><span class="sxs-lookup"><span data-stu-id="84fd6-110">In This Section</span></span>

  - [<span data-ttu-id="84fd6-111">Необходимые условия и роли для настройки объявлений в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="84fd6-111">Announcement configuration prerequisites and roles in Lync Server 2013</span></span>](lync-server-2013-announcement-configuration-prerequisites-and-roles.md)

  - [<span data-ttu-id="84fd6-112">Процесс развертывания приложения "объявление" в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="84fd6-112">Deployment process for the Announcement application in Lync Server 2013</span></span>](lync-server-2013-deployment-process-for-the-announcement-application.md)

  - [<span data-ttu-id="84fd6-113">Создание извещения в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="84fd6-113">Create an announcement in Lync Server 2013</span></span>](lync-server-2013-create-an-announcement.md)

  - [<span data-ttu-id="84fd6-114">Настройка таблицы неназначенных номеров в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="84fd6-114">Configure the unassigned number table in Lync Server 2013</span></span>](lync-server-2013-configure-the-unassigned-number-table.md)

  - [<span data-ttu-id="84fd6-115">Необязательно Проверка развертывания объявлений в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="84fd6-115">(Optional) Verify Announcement deployment in Lync Server 2013</span></span>](lync-server-2013-optional-verify-announcement-deployment.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="84fd6-116">См. также</span><span class="sxs-lookup"><span data-stu-id="84fd6-116">See Also</span></span>


[<span data-ttu-id="84fd6-117">Планирование функций управления звонками в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="84fd6-117">Planning for call management features in Lync Server 2013</span></span>](lync-server-2013-planning-for-call-management-features.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

