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
ms.openlocfilehash: 827399a74f2af29645d77f28efe9b7f2fc5fb3ce
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49818029"
---
# <a name="trunk-settings-expander"></a><span data-ttu-id="34ffb-103">Расширитель параметров магистральной линии связи</span><span class="sxs-lookup"><span data-stu-id="34ffb-103">Trunk Settings Expander</span></span>

<span data-ttu-id="34ffb-104">Чтобы изменить параметры магистральной линии SIP, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="34ffb-104">To edit or modify the settings for a SIP trunk, you do the following:</span></span>

 <span data-ttu-id="34ffb-105">**Имя линии связи** является обязательным параметром, который уникально определяет магистраль SIP в развертывании.</span><span class="sxs-lookup"><span data-stu-id="34ffb-105">**Trunk name** is a required entry and uniquely identifies the SIP trunk in the deployment.</span></span>

 <span data-ttu-id="34ffb-106">**Связанный шлюз ТСОП**. Выберите существующий шлюз ТСОП, определенный в развертывании.</span><span class="sxs-lookup"><span data-stu-id="34ffb-106">**Associated PSTN gateway**: Select an existing PSTN gateway that has been defined in the deployment.</span></span>

 <span data-ttu-id="34ffb-p101">**Порт прослушивания для IP-адреса/шлюза ТСОП**. Указывает, какой порт TCP/IP шлюза используется для прослушивание запросов. Необходимое значение может отличаться в зависимости от поставщика шлюза, однако по умолчанию используется порт 5067.</span><span class="sxs-lookup"><span data-stu-id="34ffb-p101">**Listening port for IP/PSTN gateway**: Indicates what TCP/IP port the gateway will be listening for requests on. The required value may differ, based on the vendor of the gateway, but the default is port 5067.</span></span>

 <span data-ttu-id="34ffb-p102">**Транспортный протокол SIP** может являться TCP или TLS. По умолчанию он является TLS. Сведения о протоколах, поддерживаемых шлюзом, см. в документации производителя шлюза. По умолчанию используется защищенный протокол TLS, который рекомендуется использовать для обеспечения безопасности соединений, если шлюз также поддерживает TLS.</span><span class="sxs-lookup"><span data-stu-id="34ffb-p102">**SIP Transport Protocol**: The protocol used is either TCP or TLS. TLS is the default. Refer to the gateway vendor documentation for what you gateway supports. The default is TLS, and should be considered the more secure selection, if the gateway supports TLS.</span></span>

 <span data-ttu-id="34ffb-113">**Связанный сервер-посредник:** выберите существующий сервер-посредник из развертывания, чтобы связать его с магистралью SIP.</span><span class="sxs-lookup"><span data-stu-id="34ffb-113">**Associated Mediation Server**: Select an existing Mediation Server from the deployment to associate with the SIP trunk.</span></span>

> [!NOTE]
> <span data-ttu-id="34ffb-114">Только корневую магистраль можно связывать с сервером-посредником Lync Server 2010 или Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="34ffb-114">Only the root trunk can be associated with a Lync Server 2010 or Lync Server 2013 Mediation Server.</span></span>

 <span data-ttu-id="34ffb-115">**Связанный порт сервера-посредника**: обязательное значение, задайте значение, которое сервер-посредник настроен для прослушивания.</span><span class="sxs-lookup"><span data-stu-id="34ffb-115">**Associated Mediation Server port**: A required value, this is set to the value that the Mediation Server is configured to listen on.</span></span>

![Расширитель параметров магистральной линии связи](../../media/Trunk_Settings_Expander.jpg)

## <a name="see-also"></a><span data-ttu-id="34ffb-117">См. также</span><span class="sxs-lookup"><span data-stu-id="34ffb-117">See also</span></span>

[<span data-ttu-id="34ffb-118">Контрольный список развертывания магистрали SIP</span><span class="sxs-lookup"><span data-stu-id="34ffb-118">SIP Trunking Deployment Checklist</span></span>](https://technet.microsoft.com/library/94f4f03e-19d5-4198-92be-e4076dbb959a.aspx)

[<span data-ttu-id="34ffb-119">Компоненты и топологии для распределения каналов SIP</span><span class="sxs-lookup"><span data-stu-id="34ffb-119">Components and Topologies for SIP Trunking</span></span>](https://technet.microsoft.com/library/8ed9a9d0-517e-4f36-a131-22cdafa257fa.aspx)
