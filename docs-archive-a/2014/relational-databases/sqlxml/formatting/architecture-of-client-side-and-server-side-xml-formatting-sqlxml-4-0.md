---
title: Arquitetura da formatação XML do lado do cliente e do servidor (SQLXML 4,0) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- providers [SQLXML], XML formatting architecture
- SQLOLEDB provider
- client-side XML formatting
- data providers [SQLXML], XML formatting architecture
- SQLNCLI, XML
- server-side XML formatting
- SQL Server Native Client, XML
- SQLXMLOLEDB Provider, XML formatting architecture
ms.assetid: 52440d9e-89fd-4c15-a008-a1ea99f41387
author: rothja
ms.author: jroth
ms.openlocfilehash: ae1a9c60a7a7966f4eff2a08b4557487f5aec58c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575719"
---
# <a name="architecture-of-client-side-and-server-side-xml-formatting-sqlxml-40"></a><span data-ttu-id="04b89-102">Arquitetura de formatação XML no lado do cliente e no lado do servidor (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="04b89-102">Architecture of Client-side and Server-side XML Formatting (SQLXML 4.0)</span></span>
  <span data-ttu-id="04b89-103">A ilustração a seguir mostra a arquitetura de formatação XML no lado do servidor.</span><span class="sxs-lookup"><span data-stu-id="04b89-103">The following illustration shows the architecture of XML formatting on the server side.</span></span>  
  
 <span data-ttu-id="04b89-104">![Arquitetura de formatação XML no lado do servidor.](../../../database-engine/dev-guide/media/serversidexml.gif "Arquitetura de formatação XML no lado do servidor.")</span><span class="sxs-lookup"><span data-stu-id="04b89-104">![Architecture of XML formatting on the server side.](../../../database-engine/dev-guide/media/serversidexml.gif "Architecture of XML formatting on the server side.")</span></span>  
  
 <span data-ttu-id="04b89-105">Neste exemplo, o comando especificado no cliente é enviado ao servidor.</span><span class="sxs-lookup"><span data-stu-id="04b89-105">In this example, the command that is specified on the client is sent to the server.</span></span> <span data-ttu-id="04b89-106">O servidor gera um documento XML e o retorna ao cliente.</span><span class="sxs-lookup"><span data-stu-id="04b89-106">The server produces an XML document and returns it to the client.</span></span> <span data-ttu-id="04b89-107">Nesse caso, o servidor tem uma instância do [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="04b89-107">In this case, the server has an instance of [!INCLUDE[msCoName](../../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="04b89-108">Com a formatação XML no lado do servidor, você pode usar o provedor SQLXMLOLEDB ou o provedor SQLOLEDB.</span><span class="sxs-lookup"><span data-stu-id="04b89-108">With server-side XML formatting, you can use either the SQLXMLOLEDB provider or the SQLOLEDB provider.</span></span>  <span data-ttu-id="04b89-109">O provedor SQLXMLOLEDB usa Sqlxml4.dll que é incluído no SQLXML 4.0.</span><span class="sxs-lookup"><span data-stu-id="04b89-109">The SQLXMLOLEDB provider uses Sqlxml4.dll, which is included in SQLXML 4.0.</span></span> <span data-ttu-id="04b89-110">Quando você usa o provedor SQLOLEDB, por padrão obtém a funcionalidade do SQLXML fornecida pela Sqlxmlx.dll, incluída com o [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Windows ou MDAC (Microsoft Data Access Components) 2.6 ou posterior.</span><span class="sxs-lookup"><span data-stu-id="04b89-110">When you use the SQLOLEDB provider, by default you get the SQLXML functionality provided by Sqlxmlx.dll, which is included with [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Windows or in Microsoft Data Access Components (MDAC) 2.6 or later.</span></span> <span data-ttu-id="04b89-111">Para usar Sqlxml4.dll com SQLOLEDB, você deve definir a Propriedade Version do SQLXML como "SQLXML. 4.0" no objeto de conexão SQLOLEDB.</span><span class="sxs-lookup"><span data-stu-id="04b89-111">To use Sqlxml4.dll with SQLOLEDB, you must set the SQLXML Version property to "SQLXML.4.0" on the SQLOLEDB Connection object.</span></span> <span data-ttu-id="04b89-112">Em todo caso, o servidor gera o documento XML e o envia ao cliente.</span><span class="sxs-lookup"><span data-stu-id="04b89-112">In either case, the server produces the XML document and sends it to the client.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="04b89-113">As consultas e os diagramas de atualização XPath são analisados no cliente.</span><span class="sxs-lookup"><span data-stu-id="04b89-113">XPath queries and updategrams are parsed on the client.</span></span> <span data-ttu-id="04b89-114">Para obter a funcionalidade do diagrama de atualização ou do modelo XPath no SQLXML 4.0, use Sqlxml4.dll.</span><span class="sxs-lookup"><span data-stu-id="04b89-114">To get the XPath template or updategram functionality in SQLXML 4.0, use Sqlxml4.dll.</span></span>  
  
 <span data-ttu-id="04b89-115">A ilustração a seguir mostra a arquitetura da formatação XML no lado do cliente.</span><span class="sxs-lookup"><span data-stu-id="04b89-115">The following illustration shows the architecture of XML formatting on the client side.</span></span>  
  
 <span data-ttu-id="04b89-116">![Arquitetura de formatação XML no lado do cliente.](../../../database-engine/dev-guide/media/clientsidexml.gif "Arquitetura de formatação XML no lado do cliente.")</span><span class="sxs-lookup"><span data-stu-id="04b89-116">![Architecture of XML formatting on the client side.](../../../database-engine/dev-guide/media/clientsidexml.gif "Architecture of XML formatting on the client side.")</span></span>  
  
 <span data-ttu-id="04b89-117">Neste exemplo, o cliente usa o provedor SQLXMLOLEDB.</span><span class="sxs-lookup"><span data-stu-id="04b89-117">In this example, the client uses the SQLXMLOLEDB provider.</span></span> <span data-ttu-id="04b89-118">Na cadeia de conexão, a propriedade Provedor de Dados deve ser definida como SQLOLEDB.</span><span class="sxs-lookup"><span data-stu-id="04b89-118">In the connection string, the Data Provider property must be set to SQLOLEDB.</span></span> <span data-ttu-id="04b89-119">(Esse é o único valor aceito no SQLXML 4,0.) O comando executado no cliente é enviado ao servidor.</span><span class="sxs-lookup"><span data-stu-id="04b89-119">(This is the only value accepted in SQLXML 4.0.) The command that is executed on the client is sent to the server.</span></span> <span data-ttu-id="04b89-120">O conjunto de linhas gerado no servidor é enviado ao cliente.</span><span class="sxs-lookup"><span data-stu-id="04b89-120">The rowset that is generated on the server is sent to the client.</span></span> <span data-ttu-id="04b89-121">A formatação do documento XML do conjunto de linhas é executada no cliente.</span><span class="sxs-lookup"><span data-stu-id="04b89-121">The formatting of the XML document from the rowset is performed on the client.</span></span>  
  
 <span data-ttu-id="04b89-122">No SQLXML 4.0, tanto o provedor [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client (SQLNCLI11) como o SQLOLEDB podem ser usados como o provedor de dados.</span><span class="sxs-lookup"><span data-stu-id="04b89-122">In SQLXML 4.0, either the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client (SQLNCLI11) or the SQLOLEDB provider can be used as the data provider.</span></span> <span data-ttu-id="04b89-123">Você pode acessar potencialmente qualquer fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="04b89-123">You can potentially access any data source.</span></span> <span data-ttu-id="04b89-124">Contanto que a consulta retorne um único conjunto de linhas, a transformação XML pode ser aplicada no cliente.</span><span class="sxs-lookup"><span data-stu-id="04b89-124">As long as the query returns a single rowset, the XML transformation can be applied on the client.</span></span>  
  
  
