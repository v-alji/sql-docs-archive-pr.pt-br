---
title: Diretrizes e limitações do SQLXML 4,0 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- SQLXML, about SQLXML
ms.assetid: fe433d30-90a1-421e-85c6-af13294dc18d
author: rothja
ms.author: jroth
ms.openlocfilehash: e020cbf0ac32e4c878b0b74b67e7c9c679d5d178
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87568417"
---
# <a name="guidelines-and-limitations-of-sqlxml-40"></a><span data-ttu-id="3b783-102">Diretrizes e limitações do SQLXML 4.0</span><span class="sxs-lookup"><span data-stu-id="3b783-102">Guidelines and Limitations of SQLXML 4.0</span></span>
  <span data-ttu-id="3b783-103">Lembre-se do seguinte ao trabalhar com SQLXML 4.0:</span><span class="sxs-lookup"><span data-stu-id="3b783-103">Remember the following when working with SQLXML 4.0:</span></span>  
  
-   <span data-ttu-id="3b783-104">O XML retornado como um resultado de consulta não é validado com relação ao esquema de mapeamento que gerou o XML.</span><span class="sxs-lookup"><span data-stu-id="3b783-104">XML returned as a query result is not validated against the mapping schema that generated the XML.</span></span>  
  
-   <span data-ttu-id="3b783-105">O SQLXML 4.0 inclui PROGIDs dependentes e independentes de versão.</span><span class="sxs-lookup"><span data-stu-id="3b783-105">SQLXML 4.0 includes version-independent and version-dependent PROGIDs.</span></span> <span data-ttu-id="3b783-106">É recomendável que todos os aplicativos de produção usem os PROGIDs dependentes de versão.</span><span class="sxs-lookup"><span data-stu-id="3b783-106">It is recommended that all production applications use version-dependent PROGIDs.</span></span> <span data-ttu-id="3b783-107">Isto é especialmente importante porque o SQLXML 4.0 não é completamente compatível com versões anteriores.</span><span class="sxs-lookup"><span data-stu-id="3b783-107">This is especially important because SQLXML 4.0 is not fully backward compatible.</span></span> <span data-ttu-id="3b783-108">O uso de PROGIDs dependentes de versão o protege de possíveis falhas de produção quando você instala versões mais recentes.</span><span class="sxs-lookup"><span data-stu-id="3b783-108">Using version dependent PROGIDs protects from possible production failures when you install newer releases.</span></span> <span data-ttu-id="3b783-109">De versão para versão, o comportamento do programa pode ser alterado por uma série de motivos, como correções de bug, possíveis alterações de design etc.</span><span class="sxs-lookup"><span data-stu-id="3b783-109">From release to release, program behavior may change for a variety of reasons, such as bug fixes, possible design changes, and so on.</span></span> <span data-ttu-id="3b783-110">O uso de PROGIDs dependentes de versão o protege de falhas inesperadas quando você instala versões mais recentes.</span><span class="sxs-lookup"><span data-stu-id="3b783-110">Using version-dependent PROGIDs protects from unexpected failure when you install newer releases.</span></span> <span data-ttu-id="3b783-111">Com PROGIDs dependentes de versão, quando você instala uma versão mais recente, seu aplicativo continua a operar sem falha.</span><span class="sxs-lookup"><span data-stu-id="3b783-111">With version-dependent PROGIDs, when you install a newer release, your application will continue to work without failure.</span></span> <span data-ttu-id="3b783-112">Se você decidir alterar PROGIDs dependentes de versão anteriores e usar PROGIDs dependentes de versão recentes em uma versão mais recente, deverá testar seu aplicativo antes de colocá-lo em produção.</span><span class="sxs-lookup"><span data-stu-id="3b783-112">If you decide to change the previous version-dependent PROGIDs and use the recent version-dependent PROGIDs in a newer release, you must test your application before putting it into production.</span></span> <span data-ttu-id="3b783-113">Por exemplo, aplicativos que usam os PROGIDs independentes de versão podem falhar neste cenário:</span><span class="sxs-lookup"><span data-stu-id="3b783-113">For example, applications using version-independent PROGIDs may fail in the following scenario:</span></span>  
  
     <span data-ttu-id="3b783-114">Você está executando um aplicativo que usa SQLXML 4.0 e os PROGIDs dependentes de versão, e decide instalar outro programa de software.</span><span class="sxs-lookup"><span data-stu-id="3b783-114">You are running an application that uses SQLXML 4.0 and version-independent PROGIDs, and you decide to install some other software program.</span></span> <span data-ttu-id="3b783-115">Esse programa pode instalar uma versão anterior do SQLXML.</span><span class="sxs-lookup"><span data-stu-id="3b783-115">This program might install an earlier version of SQLXML.</span></span> <span data-ttu-id="3b783-116">Seu aplicativo pode falhar, pois os PROGIDS independentes de versão do seu aplicativo agora apontam para a versão mais antiga do SQLXML, o que pode ou não possuir o recurso SQL XML que seu aplicativo está usando.</span><span class="sxs-lookup"><span data-stu-id="3b783-116">Your application may fail because the version-independent PROGIDS in your application now point to the earlier version of SQLXML, which may or may not have the SQLXML feature that your application is using.</span></span>  
  
-   <span data-ttu-id="3b783-117">Se, por algum motivo, você não quiser usar o provedor SQLXMLOLEDB e, em vez disso, quiser usar o provedor SQLOLEDB para os recursos do SQLXML, defina a propriedade **versão do SQLXML** como "SQLXML. 4.0".</span><span class="sxs-lookup"><span data-stu-id="3b783-117">If for any reason you don't want to use the SQLXMLOLEDB provider, and instead want to use the SQLOLEDB provider for SQLXML features, set the **SQLXML Version** property to "SQLXML.4.0".</span></span>  
  
  
