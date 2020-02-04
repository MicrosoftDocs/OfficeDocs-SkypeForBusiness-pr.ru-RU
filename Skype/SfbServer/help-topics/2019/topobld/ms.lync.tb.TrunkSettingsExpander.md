---
title: Расширитель настроек магистральной линии связи
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.TrunkSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3d00e8f4-e599-4094-a4a1-34fd6e8a5580
ROBOTS: NOINDEX, NOFOLLOW
description: Чтобы изменить параметры магистральной линии SIP, выполните следующие действия.
ms.openlocfilehash: b2401dd561891b5c54f22003b0a29f61933b0277
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2020
ms.locfileid: "41687942"
---
# <a name="trunk-settings-expander"></a><span data-ttu-id="8bc35-103">Расширитель настроек магистральной линии связи</span><span class="sxs-lookup"><span data-stu-id="8bc35-103">Trunk Settings Expander</span></span>

<span data-ttu-id="8bc35-104">Чтобы изменить параметры магистральной линии SIP, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="8bc35-104">To edit or modify the settings for a SIP trunk, you do the following:</span></span>

 <span data-ttu-id="8bc35-105">**Имя линии связи**. Обязательный параметр, однозначно определяющий магистраль SIP в развертывании.</span><span class="sxs-lookup"><span data-stu-id="8bc35-105">**Trunk name** is a required entry and uniquely identifies the SIP trunk in the deployment.</span></span>

 <span data-ttu-id="8bc35-106">**Связанный шлюз ТСОП**. Выберите существующий шлюз ТСОП, определенный в развертывании.</span><span class="sxs-lookup"><span data-stu-id="8bc35-106">**Associated PSTN gateway**: Select an existing PSTN gateway that has been defined in the deployment.</span></span>

 <span data-ttu-id="8bc35-p101">**Порт прослушивания для шлюза IP/ТСОП**. Порт TCP/IP, через который на шлюзе ожидается передача запросов. Обязательное значение зависит от поставщика шлюза, но по умолчанию используется порт 5067.</span><span class="sxs-lookup"><span data-stu-id="8bc35-p101">**Listening port for IP/PSTN gateway**: Indicates what TCP/IP port the gateway will be listening for requests on. The required value may differ, based on the vendor of the gateway, but the default is port 5067.</span></span>

 <span data-ttu-id="8bc35-p102">**Транспортный протокол SIP**. Допустимые протоколы: TCP и TLS. По умолчанию применяется протокол TLS. Сведения о протоколах, поддерживаемых конкретным шлюзом, см. в документации поставщика шлюза. Предпочтительным является используемый по умолчанию протокол TLS, если он поддерживается шлюзом, так как этот протокол обеспечивает повышенный уровень безопасности.</span><span class="sxs-lookup"><span data-stu-id="8bc35-p102">**SIP Transport Protocol**: The protocol used is either TCP or TLS. TLS is the default. Refer to the gateway vendor documentation for what you gateway supports. The default is TLS, and should be considered the more secure selection, if the gateway supports TLS.</span></span>

 <span data-ttu-id="8bc35-113">**Сервер связанных исправлений**: выберите существующий сервер из развертывания для связи с магистральной внешней сетью SIP.</span><span class="sxs-lookup"><span data-stu-id="8bc35-113">**Associated Mediation Server**: Select an existing Mediation Server from the deployment to associate with the SIP trunk.</span></span>

> [!NOTE]
> <span data-ttu-id="8bc35-114">На сервер-посредник может быть связана только корневая магистраль.</span><span class="sxs-lookup"><span data-stu-id="8bc35-114">Only the root trunk can be associated with a Mediation Server.</span></span>

 <span data-ttu-id="8bc35-115">**Порт сервера-относящихся к исправлению**: необходимое значение — значение, на котором настроен сервер-посредник для прослушивания.</span><span class="sxs-lookup"><span data-stu-id="8bc35-115">**Associated Mediation Server port**: A required value, this is set to the value that the Mediation Server is configured to listen on.</span></span>

![Расширитель настроек магистральной линии связи](../../../media/Trunk_Settings_Expander.jpg)

## <a name="see-also"></a><span data-ttu-id="8bc35-117">См. также</span><span class="sxs-lookup"><span data-stu-id="8bc35-117">See also</span></span>

[<span data-ttu-id="8bc35-118">Контрольный список для развертывания каналов SIP</span><span class="sxs-lookup"><span data-stu-id="8bc35-118">SIP Trunking Deployment Checklist</span></span>](https://technet.microsoft.com/library/94f4f03e-19d5-4198-92be-e4076dbb959a.aspx)

[<span data-ttu-id="8bc35-119">Компоненты и топологии для магистральной магистрали SIP</span><span class="sxs-lookup"><span data-stu-id="8bc35-119">Components and Topologies for SIP Trunking</span></span>](https://technet.microsoft.com/library/8ed9a9d0-517e-4f36-a131-22cdafa257fa.aspx)
