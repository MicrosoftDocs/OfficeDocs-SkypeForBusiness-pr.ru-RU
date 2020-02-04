---
title: Переход размещенного сервера исправлений на отдельный сервер-посредник (необязательно)
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Transition a collocated Mediation Server to a stand-alone Mediation Server (optional)
ms:assetid: 7c3c2fb4-4ff2-47b1-aab3-0aa91472eadb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205026(v=OCS.15)
ms:contentKeyID: 48184602
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2c6a76bceb935900521859911ce5398ae2213e22
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41738669"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="transition-a-collocated-mediation-server-to-a-stand-alone-mediation-server-optional"></a><span data-ttu-id="104d2-102">Переход размещенного сервера исправлений на отдельный сервер-посредник (необязательно)</span><span class="sxs-lookup"><span data-stu-id="104d2-102">Transition a collocated Mediation Server to a stand-alone Mediation Server (optional)</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="104d2-103">_**Тема последнего изменения:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="104d2-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="104d2-104">Используйте описанную ниже процедуру для перехода на сервер-посредник, размещенный на сервере Standard Edition или в пуле внешних интерфейсов, на отдельный сервер-посредник для развертывания на одном сайте.</span><span class="sxs-lookup"><span data-stu-id="104d2-104">Use the procedure that follows to transition your Mediation Server, collocated on your Standard Edition server or Front End pool, to a stand-alone Mediation Server for a single-site deployment.</span></span>

<div>

## <a name="to-transition-a-collocated-mediation-server-to-a-stand-alone-mediation-server"></a><span data-ttu-id="104d2-105">Перевод размещенного сервера исправлений на отдельный сервер-посредник</span><span class="sxs-lookup"><span data-stu-id="104d2-105">To transition a collocated Mediation Server to a stand-alone Mediation Server</span></span>

1.  <span data-ttu-id="104d2-106">Откройте существующую топологию из построителя топологии.</span><span class="sxs-lookup"><span data-stu-id="104d2-106">Open an existing topology from Topology Builder.</span></span>

2.  <span data-ttu-id="104d2-107">На левой панели перейдите к разделу **Пулы проблем**.</span><span class="sxs-lookup"><span data-stu-id="104d2-107">In the left pane, navigate to **Mediation pools**.</span></span>

3.  <span data-ttu-id="104d2-108">Щелкните правой кнопкой **Пулы** и выберите **новый сервер-посредник**.</span><span class="sxs-lookup"><span data-stu-id="104d2-108">Right-click **Mediation pools** and select **New Mediation Server**.</span></span>

4.  <span data-ttu-id="104d2-109">На странице **Определение нового пула исправлений** укажите полное доменное имя нового пула серверов-исправлений.</span><span class="sxs-lookup"><span data-stu-id="104d2-109">On the **Define New Mediation Pool** page, provide the FQDN of the new Mediation Server pool.</span></span> <span data-ttu-id="104d2-110">Кроме того, укажите, будет ли этот пул состоять из одного или нескольких серверов, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="104d2-110">Also, select whether this pool will be a single-server or multiple-server pool, and then click **Next**.</span></span>

5.  <span data-ttu-id="104d2-111">Выберите пул серверов переднего плана следующего прыжка, на который будет маршрутизироваться входящий звонок, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="104d2-111">Select the next hop Front End server pool to which the new Mediation Server will route inbound calls, and then click **Next**.</span></span>

6.  <span data-ttu-id="104d2-112">Выберите пул EDGE, который будет использоваться сервером исправлений, и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="104d2-112">Select the Edge pool to be used by the Mediation Server and then click **Next**.</span></span>

7.  <span data-ttu-id="104d2-113">На странице **указать шлюзы PSTN** свяжите предыдущий шлюз PSTN с сервером-посредником.</span><span class="sxs-lookup"><span data-stu-id="104d2-113">On the **Specify PSTN gateways** page, associate the previous PSTN gateway with the Mediation Server.</span></span> <span data-ttu-id="104d2-114">Выберите шлюз и нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="104d2-114">Select the gateway and then click **Add**.</span></span>

8.  <span data-ttu-id="104d2-115">Нажмите кнопку **Готово** , чтобы закрыть мастер **определения пула исправлений** .</span><span class="sxs-lookup"><span data-stu-id="104d2-115">Click **Finish** to close the **Define New Mediation Pool** wizard.</span></span>

9.  <span data-ttu-id="104d2-116">В **построителе топологии**выберите верхний узел **Lync Server 2013**.</span><span class="sxs-lookup"><span data-stu-id="104d2-116">From **Topology Builder**, select the top node **Lync Server 2013**.</span></span>

10. <span data-ttu-id="104d2-117">В области **Actions (действия** ) выберите пункт **топология публикации** и завершите работу мастера.</span><span class="sxs-lookup"><span data-stu-id="104d2-117">From the **Actions** pane, select **Publish Topology** and complete the wizard.</span></span>

11. <span data-ttu-id="104d2-118">Следуйте указаниям, приведенным в статье [Установка сервера исправлений на сервере Lync server 2013](lync-server-2013-install-the-files-for-mediation-server.md) в документации по развертыванию для установки файлов на новый сервер обновлений.</span><span class="sxs-lookup"><span data-stu-id="104d2-118">Follow the steps in [Install the files for Mediation Server in Lync Server 2013](lync-server-2013-install-the-files-for-mediation-server.md) in the Deployment documentation to install the files on the new Mediation Server.</span></span>

12. <span data-ttu-id="104d2-119">После установки файлов на сервер обновлений вернитесь к построителю топологии и на левой панели перейдите к группе.</span><span class="sxs-lookup"><span data-stu-id="104d2-119">After the files are installed on the Mediation Server, return to Topology Builder, and in the left pane navigate to the pool.</span></span>

13. <span data-ttu-id="104d2-120">Щелкните пул правой кнопкой мыши и выберите команду **изменить свойства**.</span><span class="sxs-lookup"><span data-stu-id="104d2-120">Right-click the pool and select **Edit Properties**.</span></span>

14. <span data-ttu-id="104d2-121">На **сервере исправлений**снимите флажок размещенный **сервер исправлений** с разделом "включен", а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="104d2-121">Under **Mediation Server**, clear the check box **Collocated Mediation Server enabled** and then click **OK**.</span></span>

15. <span data-ttu-id="104d2-122">В **построителе топологии**выберите верхний узел **Lync Server 2013**.</span><span class="sxs-lookup"><span data-stu-id="104d2-122">From **Topology Builder**, select the top node **Lync Server 2013**.</span></span>

16. <span data-ttu-id="104d2-123">В меню **действия** выберите пункт **топология публикации** и завершите работу мастера.</span><span class="sxs-lookup"><span data-stu-id="104d2-123">From the **Action** menu, select **Publish Topology** and complete the wizard.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

