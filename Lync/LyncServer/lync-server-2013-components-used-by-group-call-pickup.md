---
title: 'Lync Server 2013: компоненты, используемые для отправки группового звонка'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Components used by Group Call Pickup
ms:assetid: 45db2f23-d486-4b20-a8cf-7b48a1f9fd3a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945625(v=OCS.15)
ms:contentKeyID: 51541470
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3583ee73c78a78317b1808bde395f76dcae85149
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34841505"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="components-used-by-group-call-pickup-in-lync-server-2013"></a><span data-ttu-id="40f24-102">Компоненты, используемые для отправки группового звонка в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="40f24-102">Components used by Group Call Pickup in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="40f24-103">_**Тема последнего изменения:** 2013-01-30_</span><span class="sxs-lookup"><span data-stu-id="40f24-103">_**Topic Last Modified:** 2013-01-30_</span></span>

<span data-ttu-id="40f24-104">Отправка группового звонка автоматически разворачивается при развертывании корпоративной голосовой связи и приложения для приостановки звонков.</span><span class="sxs-lookup"><span data-stu-id="40f24-104">Group Call Pickup is automatically deployed when you deploy Enterprise Voice and the Call Park application.</span></span> <span data-ttu-id="40f24-105">Вы включаете функцию отправки группового звонка, настраивая в таблице на приостановку соединения различные диапазоны номеров, обозначенные как номера групп для отправки звонков, а затем назначая пользователям доступ к группам для отправки звонков и обеспечивая пользователям возможность раскладки группового звонка.</span><span class="sxs-lookup"><span data-stu-id="40f24-105">You enable Group Call Pickup by configuring the Call Park orbit table with separate ranges of numbers designated as call pickup group numbers, and then by assigning users to call pickup groups and enabling the users for Group Call Pickup.</span></span> <span data-ttu-id="40f24-106">Следующие компоненты Lync Server поддерживают раскладки групповых звонков.</span><span class="sxs-lookup"><span data-stu-id="40f24-106">The following Lync Server components support Group Call Pickup:</span></span>

  - <span data-ttu-id="40f24-107">\*\*\*\*   Служба приложений службы приложений предоставляет платформу для развертывания и управления едиными приложениями для обмена информацией, например с помощью приложения для парковки звонков.</span><span class="sxs-lookup"><span data-stu-id="40f24-107">**Application service**   Application service provides a platform for deploying, hosting, and managing unified communications applications, such as the Call Park application.</span></span> <span data-ttu-id="40f24-108">Служба приложений устанавливается автоматически на каждый сервер переднего плана в пуле переднего плана и на каждом сервере Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="40f24-108">Application service is automatically installed on every Front End Server in a Front End pool and on every Standard Edition server.</span></span>

  - <span data-ttu-id="40f24-109">**Приложение для приостановки звонков**   . приложение для приема звонков — одно из унифицированных приложений для обмена данными, размещенных в службе приложений.</span><span class="sxs-lookup"><span data-stu-id="40f24-109">**Call Park application**   The Call Park application is one of the unified communications applications that are hosted by Application service.</span></span> <span data-ttu-id="40f24-110">Отправка группового звонка осуществляется на основе заявления на приостановку звонков.</span><span class="sxs-lookup"><span data-stu-id="40f24-110">Group Call Pickup is based on the Call Park application.</span></span>

  - <span data-ttu-id="40f24-111">**Командная консоль**   Lync Server для управления группами отправки группового звонка используется Командная консоль Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="40f24-111">**Lync Server Management Shell**   You use Lync Server Management Shell to manage Group Call Pickup groups.</span></span>

  - <span data-ttu-id="40f24-112">**Сефаутил Resource Kit**   вы используете вспомогательную служебную программу активации компонентов расширения (сефаутил), чтобы назначать пользователей для группы приема звонков, а также включать и отключать функцию отправки звонков для пользователей.</span><span class="sxs-lookup"><span data-stu-id="40f24-112">**SEFAUtil resource kit tool**   You use the secondary extension feature activation utility (SEFAUtil) to assign users to a call pickup group and to enable or disable call pickup for users.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

