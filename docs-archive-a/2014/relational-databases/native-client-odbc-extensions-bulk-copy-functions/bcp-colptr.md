---
title: bcp_colptr | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
api_name:
- bcp_colptr
api_location:
- sqlncli11.dll
topic_type:
- apiref
helpviewer_keywords:
- bcp_colptr function
ms.assetid: 02ece13e-1da3-4f9d-b860-3177e43d2471
author: rothja
ms.author: jroth
ms.openlocfilehash: 8b725ace58ee1768fbca1a433cdea27e3e0e546e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685652"
---
# <a name="bcp_colptr"></a><span data-ttu-id="38875-102">bcp_colptr</span><span class="sxs-lookup"><span data-stu-id="38875-102">bcp_colptr</span></span>
  <span data-ttu-id="38875-103">Define o endereço de dados variáveis do programa da cópia atual no [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="38875-103">Sets the program variable data address for the current copy into [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="38875-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="38875-104">Syntax</span></span>  
  
```  
  
RETCODE bcp_colptr (  
HDBC   
hdbc  
,  
LPCBYTE   
pData  
,  
INT   
idxServerCol  
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="38875-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="38875-105">Arguments</span></span>  
 <span data-ttu-id="38875-106">*hdbc*</span><span class="sxs-lookup"><span data-stu-id="38875-106">*hdbc*</span></span>  
 <span data-ttu-id="38875-107">É o identificador de conexão ODBC habilitado para cópia em massa.</span><span class="sxs-lookup"><span data-stu-id="38875-107">Is the bulk copy-enabled ODBC connection handle.</span></span>  
  
 <span data-ttu-id="38875-108">*pData*</span><span class="sxs-lookup"><span data-stu-id="38875-108">*pData*</span></span>  
 <span data-ttu-id="38875-109">É um ponteiro para os dados a serem copiados.</span><span class="sxs-lookup"><span data-stu-id="38875-109">Is a pointer to the data to copy.</span></span> <span data-ttu-id="38875-110">Se o tipo de dados associado for um tipo de valor grande (como SQLTEXT ou SQLIMAGE), *pData* poderá ser NULL.</span><span class="sxs-lookup"><span data-stu-id="38875-110">If the bound data type is large value type (such as SQLTEXT or SQLIMAGE), *pData* can be NULL.</span></span> <span data-ttu-id="38875-111">Um *pData* nulo indica que valores de dados longos serão enviados para SQL Server em partes usando [bcp_moretext](bcp-moretext.md).</span><span class="sxs-lookup"><span data-stu-id="38875-111">A NULL *pData* indicates long data values will be sent to SQL Server in chunks using [bcp_moretext](bcp-moretext.md).</span></span>  
  
 <span data-ttu-id="38875-112">Se *pData* for definido como NULL e a coluna correspondente ao campo associado não for um tipo de valor grande, **bcp_colptr** falhará.</span><span class="sxs-lookup"><span data-stu-id="38875-112">If *pData* is set to NULL and the column corresponding to the bound field is not a large value type, **bcp_colptr** fails.</span></span>  
  
 <span data-ttu-id="38875-113">Para obter mais informações sobre tipos de valor grande, consulte [bcp_bind](bcp-bind.md)**.**</span><span class="sxs-lookup"><span data-stu-id="38875-113">For more information on large value types, see [bcp_bind](bcp-bind.md)**.**</span></span>  
  
 <span data-ttu-id="38875-114">*idxServerCol*</span><span class="sxs-lookup"><span data-stu-id="38875-114">*idxServerCol*</span></span>  
 <span data-ttu-id="38875-115">É a posição ordinal da coluna na tabela do banco de dados na qual os dados são copiados.</span><span class="sxs-lookup"><span data-stu-id="38875-115">Is the ordinal position of the column in the database table to which the data is copied.</span></span> <span data-ttu-id="38875-116">A primeira coluna em uma tabela é a coluna 1.</span><span class="sxs-lookup"><span data-stu-id="38875-116">The first column in a table is column 1.</span></span> <span data-ttu-id="38875-117">A posição ordinal de uma coluna é relatada por [SQLColumns](../native-client-odbc-api/sqlcolumns.md).</span><span class="sxs-lookup"><span data-stu-id="38875-117">The ordinal position of a column is reported by [SQLColumns](../native-client-odbc-api/sqlcolumns.md).</span></span>  
  
## <a name="returns"></a><span data-ttu-id="38875-118">Retornos</span><span class="sxs-lookup"><span data-stu-id="38875-118">Returns</span></span>  
 <span data-ttu-id="38875-119">SUCCEED ou FAIL.</span><span class="sxs-lookup"><span data-stu-id="38875-119">SUCCEED or FAIL.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="38875-120">Comentários</span><span class="sxs-lookup"><span data-stu-id="38875-120">Remarks</span></span>  
 <span data-ttu-id="38875-121">A função **bcp_colptr** permite que você altere o endereço dos dados de origem de uma determinada coluna ao copiar dados para SQL Server com [bcp_sendrow](bcp-sendrow.md).</span><span class="sxs-lookup"><span data-stu-id="38875-121">The **bcp_colptr** function allows you to change the address of source data for a particular column when copying data to SQL Server with [bcp_sendrow](bcp-sendrow.md).</span></span>  
  
 <span data-ttu-id="38875-122">Inicialmente, o ponteiro para os dados do usuário é definido por uma chamada para **bcp_bind**.</span><span class="sxs-lookup"><span data-stu-id="38875-122">Initially, the pointer to user data is set by a call to **bcp_bind**.</span></span> <span data-ttu-id="38875-123">Se o endereço de dados da variável do programa for alterado entre as chamadas para **bcp_sendrow**, você poderá chamar **bcp_colptr** para redefinir o ponteiro para os dados.</span><span class="sxs-lookup"><span data-stu-id="38875-123">If the program variable data address changes between calls to **bcp_sendrow**, you can call **bcp_colptr** to reset the pointer to the data.</span></span> <span data-ttu-id="38875-124">A próxima chamada para **bcp_sendrow** envia os dados endereçados pela chamada para **bcp_colptr**.</span><span class="sxs-lookup"><span data-stu-id="38875-124">The next call to **bcp_sendrow** sends the data addressed by the call to **bcp_colptr**.</span></span>  
  
 <span data-ttu-id="38875-125">Deve haver uma chamada **bcp_colptr** separada para cada coluna na tabela cujo endereço de dados você deseja modificar.</span><span class="sxs-lookup"><span data-stu-id="38875-125">There must be a separate **bcp_colptr** call for every column in the table whose data address you want to modify.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="38875-126">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="38875-126">See Also</span></span>  
 [<span data-ttu-id="38875-127">Bulk Copy Functions</span><span class="sxs-lookup"><span data-stu-id="38875-127">Bulk Copy Functions</span></span>](sql-server-driver-extensions-bulk-copy-functions.md)  
  
  
