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
- NOCSH
ms.custom:
- ms.lync.tb.FeMediationServiceSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 37166b87-8a43-42a6-a2aa-5a45bed8a6f3
description: 'В этом диалоговом окне можно изменить свойства параметров шлюза PSTN сервера. Вы определяете следующие параметры:'
ms.openlocfilehash: dfe3defeb7cdce787321a401ca2a5450ee6b4ab8
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41819881"
---
# <a name="front-end-mediation-service-settings-expander-for-lync-server-2010"></a><span data-ttu-id="fc366-104">Расширитель настроек службы сервера-посредника переднего плана для Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="fc366-104">Front End Mediation Service Settings Expander for Lync Server 2010</span></span>
 
<span data-ttu-id="fc366-105">В этом диалоговом окне можно изменить свойства параметров **шлюза PSTN сервера** .</span><span class="sxs-lookup"><span data-stu-id="fc366-105">You edit the properties of the **Mediation Server PSTN gateway** settings in this dialog.</span></span> <span data-ttu-id="fc366-106">Вы определяете следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="fc366-106">You define the following settings:</span></span>
  
- <span data-ttu-id="fc366-107">Если вы хотите выделять сервер, на котором установлен этот сервер, и на интерфейсных пулах, выбери размещенный **сервер исправлений** .</span><span class="sxs-lookup"><span data-stu-id="fc366-107">Select the **Collocated Mediation Server enabled** if you want to collocate the Mediation Server with this Front End Server or Front End pools.</span></span>
    
- <span data-ttu-id="fc366-108">**Порты для прослушивания**: определяет порты, которые сервер обновлений будет прослушивать.</span><span class="sxs-lookup"><span data-stu-id="fc366-108">**Listening ports**: Define the ports that the Mediation Server will listen on.</span></span> <span data-ttu-id="fc366-109">Вы можете определить порт для **TLS** или безопасности транспортного уровня, **TCP**или протокола управления транспортировкой.</span><span class="sxs-lookup"><span data-stu-id="fc366-109">You can define a port for **TLS** or transport layer security, or **TCP**, or transport control protocol.</span></span> <span data-ttu-id="fc366-110">Чтобы запись порта TCP была доступна, необходимо установить флажок **включить TCP порт**.</span><span class="sxs-lookup"><span data-stu-id="fc366-110">For the port entry for TCP to be available, you must select the check box for **Enable TCP port**.</span></span> 
    
    > [!IMPORTANT]
    > <span data-ttu-id="fc366-111">Обратитесь к документации и параметрам конфигурации для шлюза КОММУТИРУЕМой телефонной сети, чтобы определить, нужно ли включать и определять значения портов (TLS, TCP или и то, и другое).</span><span class="sxs-lookup"><span data-stu-id="fc366-111">Refer to the documentation and configuration settings for your public switched telephone network (PSTN) gateway to determine if you need to enable and define port values TLS, TCP or both.</span></span> <span data-ttu-id="fc366-112">TLS — это более безопасный протокол, использующий сертификаты для шифрования трафика между сервером-посредником и шлюзом PSTN.</span><span class="sxs-lookup"><span data-stu-id="fc366-112">TLS is a more secure protocol, using certificates to encrypt the traffic between the Mediation Server and the PSTN gateway.</span></span> <span data-ttu-id="fc366-113">Не все шлюзы PSTN поддерживают TLS.</span><span class="sxs-lookup"><span data-stu-id="fc366-113">Not all PSTN gateways support TLS.</span></span> 
  
- <span data-ttu-id="fc366-114">Список связанных и существующих значений параметров **Линия связи** (т. е. магистрали для протокола SIP), **Шлюз** (шлюз ТСОП или IP-УАТС) и **Сайт** (сайт, настроенный для магистрали и шлюза).</span><span class="sxs-lookup"><span data-stu-id="fc366-114">A listing of currently associated and existing **Trunk** (that is, Session Initiation Protocol (SIP) Trunks), **Gateway** (PSTN gateway or IP-PBX) and **Site** (configured site for the trunk and gateway).</span></span>
    
- <span data-ttu-id="fc366-p105">Выберите магистраль, шлюз и сайт, затем щелкните **По умолчанию** для применения выбранных значения по умолчанию данной службой-посредником. Для отмены применения значения по умолчанию выберите его и щелкните **Отменить по умолчанию**. После этого выберите новое значение для применения по умолчанию и щелкните **По умолчанию**.</span><span class="sxs-lookup"><span data-stu-id="fc366-p105">You select a Trunk, Gateway and Site and click **Make Default** to set the selection as the default for this Mediation service. You select the current default and click **Unmake Default** to remove the selection as the current default. You then select a new default and click **Make Default**.</span></span>
    
  <span data-ttu-id="fc366-118">**ОК**. Принятие и фиксация изменений, внесенных в диалоговом окне.</span><span class="sxs-lookup"><span data-stu-id="fc366-118">**OK** Accepts and commits changes to the dialog.</span></span>
  
  <span data-ttu-id="fc366-119">**Отмена**. Отмена изменений и закрытие диалогового окна.</span><span class="sxs-lookup"><span data-stu-id="fc366-119">**Cancel** Discards changes and closes the dialog.</span></span>
  
  <span data-ttu-id="fc366-120">**Справка**. Отображение этого экрана справки.</span><span class="sxs-lookup"><span data-stu-id="fc366-120">**Help** Displays this help screen.</span></span>
  

