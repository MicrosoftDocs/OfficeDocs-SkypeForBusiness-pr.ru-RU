---
title: Расширитель настроек магистральной линии связи
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.TrunkSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3d00e8f4-e599-4094-a4a1-34fd6e8a5580
description: Чтобы изменить параметры магистральной линии SIP, выполните следующие действия.
ms.openlocfilehash: 5859686a6fedf8c4da15ada5c4ad92f47c24b756
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51114145"
---
# <a name="trunk-settings-expander"></a><span data-ttu-id="4f59e-103">Расширитель параметров магистральной линии связи</span><span class="sxs-lookup"><span data-stu-id="4f59e-103">Trunk Settings Expander</span></span>

<span data-ttu-id="4f59e-104">Чтобы изменить параметры магистральной линии SIP, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="4f59e-104">To edit or modify the settings for a SIP trunk, you do the following:</span></span>

 <span data-ttu-id="4f59e-105">**Имя линии связи** является обязательным параметром, который уникально определяет магистраль SIP в развертывании.</span><span class="sxs-lookup"><span data-stu-id="4f59e-105">**Trunk name** is a required entry and uniquely identifies the SIP trunk in the deployment.</span></span>

 <span data-ttu-id="4f59e-106">**Связанный шлюз ТСОП**. Выберите существующий шлюз ТСОП, определенный в развертывании.</span><span class="sxs-lookup"><span data-stu-id="4f59e-106">**Associated PSTN gateway**: Select an existing PSTN gateway that has been defined in the deployment.</span></span>

 <span data-ttu-id="4f59e-p101">**Порт прослушивания для IP-адреса/шлюза ТСОП**. Указывает, какой порт TCP/IP шлюза используется для прослушивание запросов. Необходимое значение может отличаться в зависимости от поставщика шлюза, однако по умолчанию используется порт 5067.</span><span class="sxs-lookup"><span data-stu-id="4f59e-p101">**Listening port for IP/PSTN gateway**: Indicates what TCP/IP port the gateway will be listening for requests on. The required value may differ, based on the vendor of the gateway, but the default is port 5067.</span></span>

 <span data-ttu-id="4f59e-p102">**Транспортный протокол SIP** может являться TCP или TLS. По умолчанию он является TLS. Сведения о протоколах, поддерживаемых шлюзом, см. в документации производителя шлюза. По умолчанию используется защищенный протокол TLS, который рекомендуется использовать для обеспечения безопасности соединений, если шлюз также поддерживает TLS.</span><span class="sxs-lookup"><span data-stu-id="4f59e-p102">**SIP Transport Protocol**: The protocol used is either TCP or TLS. TLS is the default. Refer to the gateway vendor documentation for what you gateway supports. The default is TLS, and should be considered the more secure selection, if the gateway supports TLS.</span></span>

 <span data-ttu-id="4f59e-113">**Связанный сервер-посредник.** Выберите существующий сервер-посредник из развертывания, чтобы связать его с магистралью SIP.</span><span class="sxs-lookup"><span data-stu-id="4f59e-113">**Associated Mediation Server**: Select an existing Mediation Server from the deployment to associate with the SIP trunk.</span></span>

> [!NOTE]
> <span data-ttu-id="4f59e-114">Только корневой магистраль может быть связан с сервером-посредником Lync Server 2010 или Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4f59e-114">Only the root trunk can be associated with a Lync Server 2010 or Lync Server 2013 Mediation Server.</span></span>

 <span data-ttu-id="4f59e-115">**Связанный** порт сервера-посредника: необходимое значение, это значение задалось значению, которое настраивается для прослушивания сервера-посредника.</span><span class="sxs-lookup"><span data-stu-id="4f59e-115">**Associated Mediation Server port**: A required value, this is set to the value that the Mediation Server is configured to listen on.</span></span>

![Расширитель параметров магистральной линии связи](../../media/Trunk_Settings_Expander.jpg)

## <a name="see-also"></a><span data-ttu-id="4f59e-117">См. также</span><span class="sxs-lookup"><span data-stu-id="4f59e-117">See also</span></span>

[<span data-ttu-id="4f59e-118">Контрольный список развертывания магистральных SIP</span><span class="sxs-lookup"><span data-stu-id="4f59e-118">SIP Trunking Deployment Checklist</span></span>](/previous-versions/office/lync-server-2013/lync-server-2013-sip-trunk-deployment-checklist)

[<span data-ttu-id="4f59e-119">Компоненты и топологии для распределения каналов SIP</span><span class="sxs-lookup"><span data-stu-id="4f59e-119">Components and Topologies for SIP Trunking</span></span>](/previous-versions/office/lync-server-2013/lync-server-2013-components-and-topologies-for-sip-trunking)