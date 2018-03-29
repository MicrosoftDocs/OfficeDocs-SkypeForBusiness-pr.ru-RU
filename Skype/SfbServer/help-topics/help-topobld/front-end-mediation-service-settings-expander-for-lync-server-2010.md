---
title: Расширитель параметров службы посредника переднего плана для Lync Server 2010
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.FeMediationServiceSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 37166b87-8a43-42a6-a2aa-5a45bed8a6f3
description: 'Изменение свойств параметров шлюза ТСОП Mediation Server в этом диалоговом окне. Определите следующие параметры:'
ms.openlocfilehash: e3ec392aac08121296769a9d5170886c61c7511b
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2018
---
# <a name="front-end-mediation-service-settings-expander-for-lync-server-2010"></a><span data-ttu-id="b071f-104">Расширитель параметров службы посредника переднего плана для Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="b071f-104">Front End Mediation Service Settings Expander for Lync Server 2010</span></span>
 
<span data-ttu-id="b071f-105">Изменение свойств параметров **шлюза ТСОП Mediation Server** в этом диалоговом окне.</span><span class="sxs-lookup"><span data-stu-id="b071f-105">You edit the properties of the **Mediation Server PSTN gateway** settings in this dialog.</span></span> <span data-ttu-id="b071f-106">Определите следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="b071f-106">You define the following settings:</span></span>
  
- <span data-ttu-id="b071f-107">Выберите **включено, совмещенного сервера-посредника** , если необходимо совмещать на промежуточный сервер с этой пулов переднего плана или сервера переднего плана.</span><span class="sxs-lookup"><span data-stu-id="b071f-107">Select the **Collocated Mediation Server enabled** if you want to collocate the Mediation Server with this Front End Server or Front End pools.</span></span>
    
- <span data-ttu-id="b071f-108">**Порты прослушивания**: определение портов прослушивания сервера-посредника на.</span><span class="sxs-lookup"><span data-stu-id="b071f-108">**Listening ports**: Define the ports that the Mediation Server will listen on.</span></span> <span data-ttu-id="b071f-109">Вы можете определить порт для **TLS** или транспортного уровня безопасности или **TCP**или транспорта протокола управления.</span><span class="sxs-lookup"><span data-stu-id="b071f-109">You can define a port for **TLS** or transport layer security, or **TCP**, or transport control protocol.</span></span> <span data-ttu-id="b071f-110">Для запись порта TCP, чтобы оно было доступно необходимо установите флажок для **включения TCP-порт**.</span><span class="sxs-lookup"><span data-stu-id="b071f-110">For the port entry for TCP to be available, you must select the check box for **Enable TCP port**.</span></span> 
    
    > [!IMPORTANT]
    > <span data-ttu-id="b071f-111">Обратитесь к документации и параметров конфигурации для шлюза телефонной сети (общего пользования PSTN) для определения, если необходимо включить и определите значения портов TLS, TCP или оба.</span><span class="sxs-lookup"><span data-stu-id="b071f-111">Refer to the documentation and configuration settings for your public switched telephone network (PSTN) gateway to determine if you need to enable and define port values TLS, TCP or both.</span></span> <span data-ttu-id="b071f-112">Протокол TLS является более безопасной протокола, с помощью сертификатов для шифрования трафика между сервером-посредником и шлюзом ТСОП.</span><span class="sxs-lookup"><span data-stu-id="b071f-112">TLS is a more secure protocol, using certificates to encrypt the traffic between the Mediation Server and the PSTN gateway.</span></span> <span data-ttu-id="b071f-113">Не все шлюзы ТСОП поддерживает TLS.</span><span class="sxs-lookup"><span data-stu-id="b071f-113">Not all PSTN gateways support TLS.</span></span> 
  
- <span data-ttu-id="b071f-114">Список связанных и существующих значений параметров **Линия связи** (т. е. магистрали для протокола SIP), **Шлюз** (шлюз ТСОП или IP-УАТС) и **Сайт** (сайт, настроенный для магистрали и шлюза).</span><span class="sxs-lookup"><span data-stu-id="b071f-114">A listing of currently associated and existing **Trunk** (that is, Session Initiation Protocol (SIP) Trunks), **Gateway** (PSTN gateway or IP-PBX) and **Site** (configured site for the trunk and gateway).</span></span>
    
- <span data-ttu-id="b071f-p105">Выберите магистраль, шлюз и сайт, затем щелкните **По умолчанию** для применения выбранных значения по умолчанию данной службой-посредником. Для отмены применения значения по умолчанию выберите его и щелкните **Отменить по умолчанию**. После этого выберите новое значение для применения по умолчанию и щелкните **По умолчанию**.</span><span class="sxs-lookup"><span data-stu-id="b071f-p105">You select a Trunk, Gateway and Site and click **Make Default** to set the selection as the default for this Mediation service. You select the current default and click **Unmake Default** to remove the selection as the current default. You then select a new default and click **Make Default**.</span></span>
    
 <span data-ttu-id="b071f-118">**ОК**. Принятие и фиксация изменений, внесенных в диалоговом окне.</span><span class="sxs-lookup"><span data-stu-id="b071f-118">**OK** Accepts and commits changes to the dialog.</span></span>
  
 <span data-ttu-id="b071f-119">**Отмена**. Отмена изменений и закрытие диалогового окна.</span><span class="sxs-lookup"><span data-stu-id="b071f-119">**Cancel** Discards changes and closes the dialog.</span></span>
  
 <span data-ttu-id="b071f-120">**Справка**. Отображение этого экрана справки.</span><span class="sxs-lookup"><span data-stu-id="b071f-120">**Help** Displays this help screen.</span></span>
  

