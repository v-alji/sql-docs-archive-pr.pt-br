---
title: Executando procedimentos armazenados (OLE DB) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- stored procedures [OLE DB], executing
- OLE DB, stored procedures
- SQL Server Native Client OLE DB provider, stored procedures
ms.assetid: c77d9be9-2176-4438-8c7a-04b63ebece08
author: rothja
ms.author: jroth
ms.openlocfilehash: 2e6ce951f343002feea5aa793d0cc2092422b819
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87684153"
---
# <a name="running-stored-procedures-ole-db"></a><span data-ttu-id="f8e21-102">Executando procedimentos armazenados (OLE DB)</span><span class="sxs-lookup"><span data-stu-id="f8e21-102">Running Stored Procedures (OLE DB)</span></span>
  <span data-ttu-id="f8e21-103">Ao executar instruções, a chamada a um procedimento armazenado na fonte de dados (em vez de executar ou preparar uma instrução diretamente no aplicativo cliente) pode fornecer:</span><span class="sxs-lookup"><span data-stu-id="f8e21-103">When executing statements, calling a stored procedure on the data source (instead of executing or preparing a statement in the client application directly) can provide:</span></span>  
  
-   <span data-ttu-id="f8e21-104">Maior desempenho.</span><span class="sxs-lookup"><span data-stu-id="f8e21-104">Higher performance.</span></span>  
  
-   <span data-ttu-id="f8e21-105">Menor sobrecarga da rede.</span><span class="sxs-lookup"><span data-stu-id="f8e21-105">Reduced network overhead.</span></span>  
  
-   <span data-ttu-id="f8e21-106">Melhor consistência.</span><span class="sxs-lookup"><span data-stu-id="f8e21-106">Better consistency.</span></span>  
  
-   <span data-ttu-id="f8e21-107">Maior exatidão.</span><span class="sxs-lookup"><span data-stu-id="f8e21-107">Better accuracy.</span></span>  
  
-   <span data-ttu-id="f8e21-108">Maior funcionalidade.</span><span class="sxs-lookup"><span data-stu-id="f8e21-108">Added functionality.</span></span>  
  
 <span data-ttu-id="f8e21-109">O [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] provedor de OLE DB de cliente nativo dá suporte a três dos mecanismos que [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] os procedimentos armazenados usam para retornar dados:</span><span class="sxs-lookup"><span data-stu-id="f8e21-109">The [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client OLE DB provider supports three of the mechanisms that [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] stored procedures use to return data:</span></span>  
  
-   <span data-ttu-id="f8e21-110">Toda instrução SELECT no procedimento gera um conjunto de resultados.</span><span class="sxs-lookup"><span data-stu-id="f8e21-110">Every SELECT statement in the procedure generates a result set.</span></span>  
  
-   <span data-ttu-id="f8e21-111">O procedimento pode retornar dados através de parâmetros de saída.</span><span class="sxs-lookup"><span data-stu-id="f8e21-111">The procedure can return data through output parameters.</span></span>  
  
-   <span data-ttu-id="f8e21-112">O procedimento pode ter um código de retorno de inteiro.</span><span class="sxs-lookup"><span data-stu-id="f8e21-112">The procedure can have an integer return code.</span></span>  
  
 <span data-ttu-id="f8e21-113">O aplicativo precisa ser capaz de tratar todas essas saídas provenientes dos procedimentos armazenados.</span><span class="sxs-lookup"><span data-stu-id="f8e21-113">The application must be able to handle all of these outputs from stored procedures.</span></span>  
  
 <span data-ttu-id="f8e21-114">Provedores do OLE DB diferentes retornam parâmetros de saída e valores de retorno em horários diferentes durante o processamento de resultados.</span><span class="sxs-lookup"><span data-stu-id="f8e21-114">Different OLE DB providers return output parameters and return values at different times during result processing.</span></span> <span data-ttu-id="f8e21-115">No caso do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] provedor de OLE DB de cliente nativo, os parâmetros de saída e os códigos de retorno não são fornecidos até que o consumidor tenha recuperado ou cancelado os conjuntos de resultados retornados pelo procedimento armazenado.</span><span class="sxs-lookup"><span data-stu-id="f8e21-115">In case of the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client OLE DB provider, the output parameters and return codes are not supplied until after the consumer has retrieved or canceled the result sets returned by the stored procedure.</span></span> <span data-ttu-id="f8e21-116">Os códigos de retorno e parâmetros de saída são retornados no último pacote TDS proveniente do servidor.</span><span class="sxs-lookup"><span data-stu-id="f8e21-116">The return codes and the output parameters are returned in the last TDS packet from the server.</span></span>  
  
 <span data-ttu-id="f8e21-117">Os provedores usam a propriedade DBPROP_OUTPUTPARAMETERAVAILABILITY para informar o momento em que são retornados os parâmetros de saída e valores de retorno.</span><span class="sxs-lookup"><span data-stu-id="f8e21-117">Providers use the DBPROP_OUTPUTPARAMETERAVAILABILITY property to report when it returns output parameters and return values.</span></span> <span data-ttu-id="f8e21-118">Essa propriedade faz parte do conjunto de propriedades DBPROPSET_DATASOURCEINFO.</span><span class="sxs-lookup"><span data-stu-id="f8e21-118">This property is in the DBPROPSET_DATASOURCEINFO property set.</span></span>  
  
 <span data-ttu-id="f8e21-119">O [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] provedor de OLE DB de cliente nativo define a propriedade DBPROP_OUTPUTPARAMETERAVAILABILITY como DBPROPVAL_OA_ATROWRELEASE para indicar que os códigos de retorno e os parâmetros de saída não são retornados até que o conjunto de resultados seja processado ou liberado.</span><span class="sxs-lookup"><span data-stu-id="f8e21-119">The [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client OLE DB provider sets the DBPROP_OUTPUTPARAMETERAVAILABILITY property to DBPROPVAL_OA_ATROWRELEASE to indicate that return codes and output parameters are not returned until the result set is processed or released.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f8e21-120">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="f8e21-120">See Also</span></span>  
 [<span data-ttu-id="f8e21-121">Procedimentos armazenados</span><span class="sxs-lookup"><span data-stu-id="f8e21-121">Stored Procedures</span></span>](stored-procedures.md)  
  
  
