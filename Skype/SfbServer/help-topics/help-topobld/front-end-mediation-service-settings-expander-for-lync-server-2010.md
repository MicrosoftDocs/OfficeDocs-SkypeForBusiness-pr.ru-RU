---
title: Расширитель настроек службы сервера-посредника переднего плана для Lync Server 2010
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
ms.openlocfilehash: 37baf89b6100528c1485f939f69e20c697803123
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/23/2020
ms.locfileid: "48217730"
---
# <a name="front-end-mediation-service-settings-expander-for-lync-server-2010"></a><span data-ttu-id="ff0ec-104">Расширитель настроек службы сервера-посредника переднего плана для Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="ff0ec-104">Front End Mediation Service Settings Expander for Lync Server 2010</span></span>
 
<span data-ttu-id="ff0ec-105">В этом диалоговом окне меняются свойства параметров **Шлюз ТСОП сервера-посредника**.</span><span class="sxs-lookup"><span data-stu-id="ff0ec-105">You edit the properties of the **Mediation Server PSTN gateway** settings in this dialog.</span></span> <span data-ttu-id="ff0ec-106">Доступны для определения следующие параметры.</span><span class="sxs-lookup"><span data-stu-id="ff0ec-106">You define the following settings:</span></span>
  
- <span data-ttu-id="ff0ec-107">Выберите совмещенный **сервер-посредник** , если необходимо совместно использовать сервер-посредник с этим сервером переднего плана или интерфейсными пулами.</span><span class="sxs-lookup"><span data-stu-id="ff0ec-107">Select the **Collocated Mediation Server enabled** if you want to collocate the Mediation Server with this Front End Server or Front End pools.</span></span>
    
- <span data-ttu-id="ff0ec-108">**Порты прослушивания**: Определите порты, которые сервер-посредник должен прослушать.</span><span class="sxs-lookup"><span data-stu-id="ff0ec-108">**Listening ports**: Define the ports that the Mediation Server will listen on.</span></span> <span data-ttu-id="ff0ec-109">Можно определить порт для протокола TLS или протокола **TLS** **или протокола**управления транспортом.</span><span class="sxs-lookup"><span data-stu-id="ff0ec-109">You can define a port for **TLS** or transport layer security, or **TCP**, or transport control protocol.</span></span> <span data-ttu-id="ff0ec-110">Чтобы запись порта TCP была доступна, необходимо установить флажок **включить порт TCP**.</span><span class="sxs-lookup"><span data-stu-id="ff0ec-110">For the port entry for TCP to be available, you must select the check box for **Enable TCP port**.</span></span> 
    
    > [!IMPORTANT]
    > <span data-ttu-id="ff0ec-111">Обратитесь к документации и параметрам конфигурации своего шлюза ТСОП, чтобы определить, требуется ли включить и задать значения портов для TLS, для TCP или для обоих этих протоколов.</span><span class="sxs-lookup"><span data-stu-id="ff0ec-111">Refer to the documentation and configuration settings for your public switched telephone network (PSTN) gateway to determine if you need to enable and define port values TLS, TCP or both.</span></span> <span data-ttu-id="ff0ec-112">TLS — это более безопасный протокол, использующий сертификаты для шифрования трафика между сервером-посредником и шлюзом PSTN.</span><span class="sxs-lookup"><span data-stu-id="ff0ec-112">TLS is a more secure protocol, using certificates to encrypt the traffic between the Mediation Server and the PSTN gateway.</span></span> <span data-ttu-id="ff0ec-113">TLS поддерживают не все шлюзы ТСОП.</span><span class="sxs-lookup"><span data-stu-id="ff0ec-113">Not all PSTN gateways support TLS.</span></span> 
  
- <span data-ttu-id="ff0ec-114">Указание назначенных и существующих значений **Линия связи** (то есть линия связи протокола SIP), **Шлюз** (шлюз ТСОП или IP-АТС) и **Сайт** (сайт, настроенный для линии связи и шлюза).</span><span class="sxs-lookup"><span data-stu-id="ff0ec-114">A listing of currently associated and existing **Trunk** (that is, Session Initiation Protocol (SIP) Trunks), **Gateway** (PSTN gateway or IP-PBX) and **Site** (configured site for the trunk and gateway).</span></span>
    
- <span data-ttu-id="ff0ec-p105">Выберите линию связи, шлюз и сайт, а затем щелкните элемент **По умолчанию**, чтобы установить выбранные значения в качестве используемых по умолчанию для данного сервера-посредника. Выберите текущее значение по умолчанию и щелкните элемент **Отменить по умолчанию**, чтобы отменить использование этого значения по умолчанию. После этого выберите новое значение по умолчанию и щелкните элемент **По умолчанию**.</span><span class="sxs-lookup"><span data-stu-id="ff0ec-p105">You select a Trunk, Gateway and Site and click **Make Default** to set the selection as the default for this Mediation service. You select the current default and click **Unmake Default** to remove the selection as the current default. You then select a new default and click **Make Default**.</span></span>
    
  <span data-ttu-id="ff0ec-118">При нажатии кнопки **ОК** выполняется принятие и сохранение изменений в этом диалоговом окне.</span><span class="sxs-lookup"><span data-stu-id="ff0ec-118">**OK** Accepts and commits changes to the dialog.</span></span>
  
  <span data-ttu-id="ff0ec-119">При нажатии кнопки **Отмена** изменения отменяются, а диалоговое окно закрывается.</span><span class="sxs-lookup"><span data-stu-id="ff0ec-119">**Cancel** Discards changes and closes the dialog.</span></span>
  
  <span data-ttu-id="ff0ec-120">При нажатии кнопки **Справка** отображается данный экран справки.</span><span class="sxs-lookup"><span data-stu-id="ff0ec-120">**Help** Displays this help screen.</span></span>
  

