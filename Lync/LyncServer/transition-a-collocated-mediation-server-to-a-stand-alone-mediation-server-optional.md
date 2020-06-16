---
title: Перевод совмещенного сервера-посредника на автономный сервер-посредник (необязательно)
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Transition a collocated Mediation Server to a stand-alone Mediation Server (optional)
ms:assetid: 7c3c2fb4-4ff2-47b1-aab3-0aa91472eadb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205026(v=OCS.15)
ms:contentKeyID: 48184602
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0ce0228edacba502161c4d44a6a94b38cede6655
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/16/2020
ms.locfileid: "44755693"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="transition-a-collocated-mediation-server-to-a-stand-alone-mediation-server-optional"></a><span data-ttu-id="2f720-102">Перевод совмещенного сервера-посредника на автономный сервер-посредник (необязательно)</span><span class="sxs-lookup"><span data-stu-id="2f720-102">Transition a collocated Mediation Server to a stand-alone Mediation Server (optional)</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2f720-103">_**Последнее изменение темы:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="2f720-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="2f720-104">Используйте следующую процедуру для переноса сервера-посредника, совместно размещаемого на сервере Standard Edition или в пуле переднего плана, на автономный сервер-посредник для развертывания на одном сайте.</span><span class="sxs-lookup"><span data-stu-id="2f720-104">Use the procedure that follows to transition your Mediation Server, collocated on your Standard Edition server or Front End pool, to a stand-alone Mediation Server for a single-site deployment.</span></span>

<div>

## <a name="to-transition-a-collocated-mediation-server-to-a-stand-alone-mediation-server"></a><span data-ttu-id="2f720-105">Перенос совместно размещаемого сервера-посредника на автономный сервер-посредник</span><span class="sxs-lookup"><span data-stu-id="2f720-105">To transition a collocated Mediation Server to a stand-alone Mediation Server</span></span>

1.  <span data-ttu-id="2f720-106">Откройте существующую топологию в окне построителя топологий.</span><span class="sxs-lookup"><span data-stu-id="2f720-106">Open an existing topology from Topology Builder.</span></span>

2.  <span data-ttu-id="2f720-107">В левой области перейдите к узлу **Пулы-посредники**.</span><span class="sxs-lookup"><span data-stu-id="2f720-107">In the left pane, navigate to **Mediation pools**.</span></span>

3.  <span data-ttu-id="2f720-108">Щелкните правой кнопкой **Пулы-посредники** и выберите команду **Создать сервер-посредник**.</span><span class="sxs-lookup"><span data-stu-id="2f720-108">Right-click **Mediation pools** and select **New Mediation Server**.</span></span>

4.  <span data-ttu-id="2f720-109">On the **Define New Mediation Pool** page, provide the FQDN of the new Mediation Server pool.</span><span class="sxs-lookup"><span data-stu-id="2f720-109">On the **Define New Mediation Pool** page, provide the FQDN of the new Mediation Server pool.</span></span> <span data-ttu-id="2f720-110">Also, select whether this pool will be a single-server or multiple-server pool, and then click **Next**.</span><span class="sxs-lookup"><span data-stu-id="2f720-110">Also, select whether this pool will be a single-server or multiple-server pool, and then click **Next**.</span></span>

5.  <span data-ttu-id="2f720-111">Выберите пул серверов переднего плана следующего прыжка, в который сервер-посредник будут направлять входящие звонки, а затем нажмите **Далее**.</span><span class="sxs-lookup"><span data-stu-id="2f720-111">Select the next hop Front End server pool to which the new Mediation Server will route inbound calls, and then click **Next**.</span></span>

6.  <span data-ttu-id="2f720-112">Выберите пограничный пул для использования этим сервером-посредником и нажмите **Далее**.</span><span class="sxs-lookup"><span data-stu-id="2f720-112">Select the Edge pool to be used by the Mediation Server and then click **Next**.</span></span>

7.  <span data-ttu-id="2f720-113">On the **Specify PSTN gateways** page, associate the previous PSTN gateway with the Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="2f720-113">On the **Specify PSTN gateways** page, associate the previous PSTN gateway with the Mediation Server.</span></span> <span data-ttu-id="2f720-114">Select the gateway and then click **Add**.</span><span class="sxs-lookup"><span data-stu-id="2f720-114">Select the gateway and then click **Add**.</span></span>

8.  <span data-ttu-id="2f720-115">Нажмите кнопку **Готово**, чтобы закрыть мастер **Определение нового пула-посредника**.</span><span class="sxs-lookup"><span data-stu-id="2f720-115">Click **Finish** to close the **Define New Mediation Pool** wizard.</span></span>

9.  <span data-ttu-id="2f720-116">В **построителе топологий**выберите верхний узел **Lync Server 2013**.</span><span class="sxs-lookup"><span data-stu-id="2f720-116">From **Topology Builder**, select the top node **Lync Server 2013**.</span></span>

10. <span data-ttu-id="2f720-117">В области **Действия** выберите команду **Опубликовать топологию** и завершите работу мастера.</span><span class="sxs-lookup"><span data-stu-id="2f720-117">From the **Actions** pane, select **Publish Topology** and complete the wizard.</span></span>

11. <span data-ttu-id="2f720-118">Выполните действия, описанные в статье [Установка файлов для сервера-посредника в Lync server 2013](lync-server-2013-install-the-files-for-mediation-server.md) , в документации по развертыванию, чтобы установить файлы на новый сервер-посредник.</span><span class="sxs-lookup"><span data-stu-id="2f720-118">Follow the steps in [Install the files for Mediation Server in Lync Server 2013](lync-server-2013-install-the-files-for-mediation-server.md) in the Deployment documentation to install the files on the new Mediation Server.</span></span>

12. <span data-ttu-id="2f720-119">После установки файлов на сервер-посредник вернитесь к построителю топологий и в левой области перейдите к пулу.</span><span class="sxs-lookup"><span data-stu-id="2f720-119">After the files are installed on the Mediation Server, return to Topology Builder, and in the left pane navigate to the pool.</span></span>

13. <span data-ttu-id="2f720-120">Щелкните пул правой кнопкой и выберите команду **Изменить свойства**.</span><span class="sxs-lookup"><span data-stu-id="2f720-120">Right-click the pool and select **Edit Properties**.</span></span>

14. <span data-ttu-id="2f720-121">В разделе **Сервер-посредник** снимите флажок **Сервер-посредник с совмещенным расположением включен** и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="2f720-121">Under **Mediation Server**, clear the check box **Collocated Mediation Server enabled** and then click **OK**.</span></span>

15. <span data-ttu-id="2f720-122">В **построителе топологий**выберите верхний узел **Lync Server 2013**.</span><span class="sxs-lookup"><span data-stu-id="2f720-122">From **Topology Builder**, select the top node **Lync Server 2013**.</span></span>

16. <span data-ttu-id="2f720-123">В меню **Макрокоманда** выберите **Публикация топологии** и выполните мастер.</span><span class="sxs-lookup"><span data-stu-id="2f720-123">From the **Action** menu, select **Publish Topology** and complete the wizard.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

