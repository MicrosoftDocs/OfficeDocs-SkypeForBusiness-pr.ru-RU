---
title: Расширитель настроек службы сервера-посредника переднего плана для Lync Server 2010
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.FeMediationServiceSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 37166b87-8a43-42a6-a2aa-5a45bed8a6f3
description: В этом диалоговом окне меняются свойства параметров Шлюз ТСОП сервера-посредника. Доступны для определения следующие параметры.
ms.openlocfilehash: ad6aab0ce528db01621b1d43a62624d96649e66a
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49807059"
---
# <a name="front-end-mediation-service-settings-expander-for-lync-server-2010"></a><span data-ttu-id="bf90b-104">Расширитель параметров службы сервера-посредника переднего плана для Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="bf90b-104">Front End Mediation Service Settings Expander for Lync Server 2010</span></span>
 
<span data-ttu-id="bf90b-105">В этом диалоговом окне меняются свойства параметров **Шлюз ТСОП сервера-посредника**.</span><span class="sxs-lookup"><span data-stu-id="bf90b-105">You edit the properties of the **Mediation Server PSTN gateway** settings in this dialog.</span></span> <span data-ttu-id="bf90b-106">Доступны для определения следующие параметры.</span><span class="sxs-lookup"><span data-stu-id="bf90b-106">You define the following settings:</span></span>
  
- <span data-ttu-id="bf90b-107">Выберите **сервер-посредник** с совмедом, если вы хотите выполнив его с этим сервером переднего или переднего серверов.</span><span class="sxs-lookup"><span data-stu-id="bf90b-107">Select the **Collocated Mediation Server enabled** if you want to collocate the Mediation Server with this Front End Server or Front End pools.</span></span>
    
- <span data-ttu-id="bf90b-108">**Порты прослушивания:** определите порты, которые будет прослушивать сервер-посредник.</span><span class="sxs-lookup"><span data-stu-id="bf90b-108">**Listening ports**: Define the ports that the Mediation Server will listen on.</span></span> <span data-ttu-id="bf90b-109">Можно определить порт для **протокола TLS** или транспортного уровня, **TCP** или протокола управления транспортировкой.</span><span class="sxs-lookup"><span data-stu-id="bf90b-109">You can define a port for **TLS** or transport layer security, or **TCP**, or transport control protocol.</span></span> <span data-ttu-id="bf90b-110">Чтобы запись порта для TCP была доступна, необходимо выбрать пункт "Включить **TCP-порт".**</span><span class="sxs-lookup"><span data-stu-id="bf90b-110">For the port entry for TCP to be available, you must select the check box for **Enable TCP port**.</span></span> 
    
    > [!IMPORTANT]
    > <span data-ttu-id="bf90b-111">Обратитесь к документации и параметрам конфигурации своего шлюза ТСОП, чтобы определить, требуется ли включить и задать значения портов для TLS, для TCP или для обоих этих протоколов.</span><span class="sxs-lookup"><span data-stu-id="bf90b-111">Refer to the documentation and configuration settings for your public switched telephone network (PSTN) gateway to determine if you need to enable and define port values TLS, TCP or both.</span></span> <span data-ttu-id="bf90b-112">TLS — это более безопасный протокол, использующий сертификаты для шифрования трафика между сервером-посредником и шлюзом STN.</span><span class="sxs-lookup"><span data-stu-id="bf90b-112">TLS is a more secure protocol, using certificates to encrypt the traffic between the Mediation Server and the PSTN gateway.</span></span> <span data-ttu-id="bf90b-113">TLS поддерживают не все шлюзы ТСОП.</span><span class="sxs-lookup"><span data-stu-id="bf90b-113">Not all PSTN gateways support TLS.</span></span> 
  
- <span data-ttu-id="bf90b-114">Указание назначенных и существующих значений **Линия связи** (то есть линия связи протокола SIP), **Шлюз** (шлюз ТСОП или IP-АТС) и **Сайт** (сайт, настроенный для линии связи и шлюза).</span><span class="sxs-lookup"><span data-stu-id="bf90b-114">A listing of currently associated and existing **Trunk** (that is, Session Initiation Protocol (SIP) Trunks), **Gateway** (PSTN gateway or IP-PBX) and **Site** (configured site for the trunk and gateway).</span></span>
    
- <span data-ttu-id="bf90b-p105">Выберите линию связи, шлюз и сайт, а затем щелкните элемент **По умолчанию**, чтобы установить выбранные значения в качестве используемых по умолчанию для данного сервера-посредника. Выберите текущее значение по умолчанию и щелкните элемент **Отменить по умолчанию**, чтобы отменить использование этого значения по умолчанию. После этого выберите новое значение по умолчанию и щелкните элемент **По умолчанию**.</span><span class="sxs-lookup"><span data-stu-id="bf90b-p105">You select a Trunk, Gateway and Site and click **Make Default** to set the selection as the default for this Mediation service. You select the current default and click **Unmake Default** to remove the selection as the current default. You then select a new default and click **Make Default**.</span></span>
    
  <span data-ttu-id="bf90b-118">При нажатии кнопки **ОК** выполняется принятие и сохранение изменений в этом диалоговом окне.</span><span class="sxs-lookup"><span data-stu-id="bf90b-118">**OK** Accepts and commits changes to the dialog.</span></span>
  
  <span data-ttu-id="bf90b-119">При нажатии кнопки **Отмена** изменения отменяются, а диалоговое окно закрывается.</span><span class="sxs-lookup"><span data-stu-id="bf90b-119">**Cancel** Discards changes and closes the dialog.</span></span>
  
  <span data-ttu-id="bf90b-120">При нажатии кнопки **Справка** отображается данный экран справки.</span><span class="sxs-lookup"><span data-stu-id="bf90b-120">**Help** Displays this help screen.</span></span>
  

