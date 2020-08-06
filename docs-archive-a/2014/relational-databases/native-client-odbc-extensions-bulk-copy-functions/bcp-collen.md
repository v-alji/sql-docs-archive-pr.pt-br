---
title: bcp_collen | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
api_name:
- bcp_collen
api_location:
- sqlncli11.dll
topic_type:
- apiref
helpviewer_keywords:
- bcp_collen function
ms.assetid: faaf1f7a-81f2-4852-a178-56602c33673a
author: rothja
ms.author: jroth
ms.openlocfilehash: 3099e26b0c2cd0d1cfee7578f5b149b812f01765
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685650"
---
# <a name="bcp_collen"></a><span data-ttu-id="dd4c4-102">bcp_collen</span><span class="sxs-lookup"><span data-stu-id="dd4c4-102">bcp_collen</span></span>
  <span data-ttu-id="dd4c4-103">Define o comprimento de dados na variável de programa para a cópia em massa atual no [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="dd4c4-103">Sets the data length in the program variable for the current bulk copy into [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dd4c4-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="dd4c4-104">Syntax</span></span>  
  
```  
  
RETCODE bcp_collen (  
HDBC   
hdbc  
,  
DBINT   
cbData  
,  
INT   
idxServerCol  
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="dd4c4-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="dd4c4-105">Arguments</span></span>  
 <span data-ttu-id="dd4c4-106">*hdbc*</span><span class="sxs-lookup"><span data-stu-id="dd4c4-106">*hdbc*</span></span>  
 <span data-ttu-id="dd4c4-107">É o identificador de conexão ODBC habilitado para cópia em massa.</span><span class="sxs-lookup"><span data-stu-id="dd4c4-107">Is the bulk copy-enabled ODBC connection handle.</span></span>  
  
 <span data-ttu-id="dd4c4-108">*cbData*</span><span class="sxs-lookup"><span data-stu-id="dd4c4-108">*cbData*</span></span>  
 <span data-ttu-id="dd4c4-109">É o comprimento dos dados na variável de programa, não incluindo o comprimento dos indicadores ou terminadores de comprimento.</span><span class="sxs-lookup"><span data-stu-id="dd4c4-109">Is the length of the data in the program variable, not including the length of any length indicator or terminator.</span></span> <span data-ttu-id="dd4c4-110">A definição de *cbData* como SQL_NULL_DATA indica que todas as linhas copiadas no servidor contêm um valor NULL na coluna.</span><span class="sxs-lookup"><span data-stu-id="dd4c4-110">Setting *cbData* to SQL_NULL_DATA indicates all rows copied to the server contain a NULL value for the column.</span></span> <span data-ttu-id="dd4c4-111">Defini-lo como SQL_VARLEN_DATA indica que um terminador da cadeia de caracteres ou outro método é usado para determinar o comprimento dos dados copiados.</span><span class="sxs-lookup"><span data-stu-id="dd4c4-111">Setting it to SQL_VARLEN_DATA indicates that a string terminator or other method is used to determine the length of data copied.</span></span> <span data-ttu-id="dd4c4-112">Se um indicador de comprimento e um terminador existirem, o sistema usará o que resultar em menos cópia de dados.</span><span class="sxs-lookup"><span data-stu-id="dd4c4-112">If both a length indicator and a terminator exist, the system uses whichever one results in less data being copied.</span></span>  
  
 <span data-ttu-id="dd4c4-113">*idxServerCol*</span><span class="sxs-lookup"><span data-stu-id="dd4c4-113">*idxServerCol*</span></span>  
 <span data-ttu-id="dd4c4-114">É a posição ordinal da coluna na tabela na qual os dados são copiados.</span><span class="sxs-lookup"><span data-stu-id="dd4c4-114">Is the ordinal position of the column in the table to which the data is copied.</span></span> <span data-ttu-id="dd4c4-115">A primeira coluna é 1.</span><span class="sxs-lookup"><span data-stu-id="dd4c4-115">The first column is 1.</span></span> <span data-ttu-id="dd4c4-116">A posição ordinal de uma coluna é relatada por [SQLColumns](../native-client-odbc-api/sqlcolumns.md).</span><span class="sxs-lookup"><span data-stu-id="dd4c4-116">The ordinal position of a column is reported by [SQLColumns](../native-client-odbc-api/sqlcolumns.md).</span></span>  
  
## <a name="returns"></a><span data-ttu-id="dd4c4-117">Retornos</span><span class="sxs-lookup"><span data-stu-id="dd4c4-117">Returns</span></span>  
 <span data-ttu-id="dd4c4-118">SUCCEED ou FAIL.</span><span class="sxs-lookup"><span data-stu-id="dd4c4-118">SUCCEED or FAIL.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="dd4c4-119">Comentários</span><span class="sxs-lookup"><span data-stu-id="dd4c4-119">Remarks</span></span>  
 <span data-ttu-id="dd4c4-120">A função **bcp_collen** permite que você altere o comprimento de dados na variável do programa para uma coluna específica quando copiar dados no [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] com [bcp_sendrow](bcp-sendrow.md).</span><span class="sxs-lookup"><span data-stu-id="dd4c4-120">The **bcp_collen** function allows you to change the data length in the program variable for a particular column when copying data to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] with [bcp_sendrow](bcp-sendrow.md).</span></span>  
  
 <span data-ttu-id="dd4c4-121">Inicialmente, o comprimento de dados é determinado quando [bcp_bind](bcp-bind.md) é chamado.</span><span class="sxs-lookup"><span data-stu-id="dd4c4-121">Initially, the data length is determined when [bcp_bind](bcp-bind.md) is called.</span></span> <span data-ttu-id="dd4c4-122">Se o comprimento de dados for alterado entre as chamadas para **bcp_sendrow** e nenhum prefixo de comprimento ou terminador for usado, você poderá chamar **bcp_collen** para redefinir o comprimento.</span><span class="sxs-lookup"><span data-stu-id="dd4c4-122">If the data length changes between calls to **bcp_sendrow** and no length prefix or terminator is being used, you can call **bcp_collen** to reset the length.</span></span> <span data-ttu-id="dd4c4-123">A próxima chamada para **bcp_sendrow** usará o comprimento definido pela chamada para **bcp_collen**.</span><span class="sxs-lookup"><span data-stu-id="dd4c4-123">The next call to **bcp_sendrow** uses the length set by the call to **bcp_collen**.</span></span>  
  
 <span data-ttu-id="dd4c4-124">Você deve chamar **bcp_collen** uma vez para cada coluna na tabela cujo comprimento de dados deseje modificar.</span><span class="sxs-lookup"><span data-stu-id="dd4c4-124">You must call **bcp_collen** once for each column in the table whose data length you want to modify.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dd4c4-125">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="dd4c4-125">See Also</span></span>  
 [<span data-ttu-id="dd4c4-126">Bulk Copy Functions</span><span class="sxs-lookup"><span data-stu-id="dd4c4-126">Bulk Copy Functions</span></span>](sql-server-driver-extensions-bulk-copy-functions.md)  
  
  
