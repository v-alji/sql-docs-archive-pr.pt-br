---
title: srv_describe (API de Procedimento Armazenado Estendido) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: stored-procedures
ms.topic: reference
api_name:
- srv_describe
api_location:
- opends60.dll
topic_type:
- apiref
dev_langs:
- C++
helpviewer_keywords:
- srv_describe
ms.assetid: 2115600e-5ce7-4be0-9cd3-a1dd1fab0729
author: rothja
ms.author: jroth
ms.openlocfilehash: 52a397b79f4fcecaa2ccacde7500cb852ae793fd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87583057"
---
# <a name="srv_describe-extended-stored-procedure-api"></a><span data-ttu-id="7385c-102">srv_describe (API de procedimento armazenado estendido)</span><span class="sxs-lookup"><span data-stu-id="7385c-102">srv_describe (Extended Stored Procedure API)</span></span>
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="7385c-103">Em vez disso, use a Integração CLR.</span><span class="sxs-lookup"><span data-stu-id="7385c-103">Use CLR integration instead.</span></span>  
  
 <span data-ttu-id="7385c-104">Define o nome da coluna e os tipos de dados da origem e do destino de uma coluna específica em sequência.</span><span class="sxs-lookup"><span data-stu-id="7385c-104">Defines the column name and source and destination data types for a specific column in a row.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7385c-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="7385c-105">Syntax</span></span>  
  
```  
  
int srv_describe (  
SRV_PROC *  
srvproc  
,  
int  
colnumber  
,  
DBCHAR *  
column_name  
,  
int  
namelen  
,  
DBINT  
desttype  
,  
DBINT  
destlen  
,  
DBINT  
srctype  
,  
DBINT  
srclen  
,  
void *  
srcdata  
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="7385c-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="7385c-106">Arguments</span></span>  
 <span data-ttu-id="7385c-107">*srvproc*</span><span class="sxs-lookup"><span data-stu-id="7385c-107">*srvproc*</span></span>  
 <span data-ttu-id="7385c-108">Trata-se de um ponteiro para a estrutura SRV_PROC, que é o identificador de uma conexão de cliente específica (nesse caso, o cliente que envia a linha).</span><span class="sxs-lookup"><span data-stu-id="7385c-108">Is a pointer to the SRV_PROC structure that is the handle for a particular client connection (in this case, the client sending the row).</span></span> <span data-ttu-id="7385c-109">A estrutura contém todas as informações que a biblioteca de APIs de Procedimento Armazenado Estendido usa para gerenciar as comunicações e os dados entre o aplicativo e o cliente.</span><span class="sxs-lookup"><span data-stu-id="7385c-109">The structure contains all the information that the Extended Stored Procedure API library uses to manage communications and data between the application and the client.</span></span>  
  
 <span data-ttu-id="7385c-110">*colnumber*</span><span class="sxs-lookup"><span data-stu-id="7385c-110">*colnumber*</span></span>  
 <span data-ttu-id="7385c-111">Atualmente ele não tem suporte.</span><span class="sxs-lookup"><span data-stu-id="7385c-111">Is currently not supported.</span></span> <span data-ttu-id="7385c-112">As colunas devem ser descritas em ordem.</span><span class="sxs-lookup"><span data-stu-id="7385c-112">Columns must be described in order.</span></span> <span data-ttu-id="7385c-113">Todas as colunas devem ser descritas antes de **srv_sendrow** ser chamado.</span><span class="sxs-lookup"><span data-stu-id="7385c-113">All columns must be described before **srv_sendrow** is called.</span></span>  
  
 <span data-ttu-id="7385c-114">*column_name*</span><span class="sxs-lookup"><span data-stu-id="7385c-114">*column_name*</span></span>  
 <span data-ttu-id="7385c-115">Especifica o nome da coluna à qual pertencem os dados.</span><span class="sxs-lookup"><span data-stu-id="7385c-115">Specifies the name of the column to which the data belongs.</span></span> <span data-ttu-id="7385c-116">Esse parâmetro pode ser NULL, porque não é obrigatório que uma coluna tenha um nome.</span><span class="sxs-lookup"><span data-stu-id="7385c-116">This parameter can be NULL because a column is not required to have a name.</span></span>  
  
 <span data-ttu-id="7385c-117">*namelen*</span><span class="sxs-lookup"><span data-stu-id="7385c-117">*namelen*</span></span>  
 <span data-ttu-id="7385c-118">Especifica o tamanho, em bytes, de *column_name*.</span><span class="sxs-lookup"><span data-stu-id="7385c-118">Specifies the length, in bytes, of *column_name*.</span></span> <span data-ttu-id="7385c-119">Se *namelen* for SRV_NULLTERM, *column_name* deverá terminar em nulo.</span><span class="sxs-lookup"><span data-stu-id="7385c-119">If *namelen* is SRV_NULLTERM, then *column_name* must be null-terminated.</span></span>  
  
 <span data-ttu-id="7385c-120">*desttype*</span><span class="sxs-lookup"><span data-stu-id="7385c-120">*desttype*</span></span>  
 <span data-ttu-id="7385c-121">Especifica o tipo de dados da coluna da linha de destino.</span><span class="sxs-lookup"><span data-stu-id="7385c-121">Specifies the data type of the destination row column.</span></span> <span data-ttu-id="7385c-122">Trata-se do tipo de dados enviado ao cliente.</span><span class="sxs-lookup"><span data-stu-id="7385c-122">This is the data type sent to the client.</span></span> <span data-ttu-id="7385c-123">O tipo de dados deverá ser especificado mesmo se os dados forem NULL; para obter mais informações, consulte [Tipos de dados &#40;API de Procedimento Armazenado Estendido&#41;](data-types-extended-stored-procedure-api.md).</span><span class="sxs-lookup"><span data-stu-id="7385c-123">The data type must be specified even if the data is NULL, for more information, see [Data Types &#40;Extended Stored Procedure API&#41;](data-types-extended-stored-procedure-api.md).</span></span>  
  
 <span data-ttu-id="7385c-124">*destlen*</span><span class="sxs-lookup"><span data-stu-id="7385c-124">*destlen*</span></span>  
 <span data-ttu-id="7385c-125">Especifica o comprimento, em bytes, dos dados a serem enviados ao cliente.</span><span class="sxs-lookup"><span data-stu-id="7385c-125">Specifies the length, in bytes, of the data to be sent to the client.</span></span> <span data-ttu-id="7385c-126">Para tipos de dados de comprimento fixo que não permitem valores nulos, *destlen* é ignorado.</span><span class="sxs-lookup"><span data-stu-id="7385c-126">For fixed-length data types that do not allow null values, *destlen* is ignored.</span></span> <span data-ttu-id="7385c-127">Para tipos de dados de comprimento variável e tipos de dados de comprimento fixo que permitem valores nulos, *destlen* especifica o tamanho máximo que os dados de destino podem ter.</span><span class="sxs-lookup"><span data-stu-id="7385c-127">For variable-length data types and fixed-length data types that allow null values, *destlen* specifies the maximum length the destination data can be.</span></span>  
  
 <span data-ttu-id="7385c-128">*srctype*</span><span class="sxs-lookup"><span data-stu-id="7385c-128">*srctype*</span></span>  
 <span data-ttu-id="7385c-129">Especifica o tipo dos dados de origem.</span><span class="sxs-lookup"><span data-stu-id="7385c-129">Specifies the data type of the source data.</span></span>  
  
 <span data-ttu-id="7385c-130">*srclen*</span><span class="sxs-lookup"><span data-stu-id="7385c-130">*srclen*</span></span>  
 <span data-ttu-id="7385c-131">Especifica o comprimento, em bytes, dos dados de origem.</span><span class="sxs-lookup"><span data-stu-id="7385c-131">Specifies the length, in bytes, of the source data.</span></span> <span data-ttu-id="7385c-132">Esse valor é ignorado em tipos de dados de comprimento fixo.</span><span class="sxs-lookup"><span data-stu-id="7385c-132">This value is ignored for fixed-length data types.</span></span>  
  
 <span data-ttu-id="7385c-133">*srcdata*</span><span class="sxs-lookup"><span data-stu-id="7385c-133">*srcdata*</span></span>  
 <span data-ttu-id="7385c-134">Fornece o endereço dos dados de origem de uma determinada coluna.</span><span class="sxs-lookup"><span data-stu-id="7385c-134">Provides the source data address for a particular column.</span></span> <span data-ttu-id="7385c-135">Quando **srv_sendrow** é chamado, ele procura os dados de *colnumber* em *srcdata*.</span><span class="sxs-lookup"><span data-stu-id="7385c-135">When **srv_sendrow** is called, it looks for the data for *colnumber* at *srcdata*.</span></span> <span data-ttu-id="7385c-136">Por isso, ele não deve ser liberado antes de uma chamada para **srv_sendrow**.</span><span class="sxs-lookup"><span data-stu-id="7385c-136">Therefore it should not be freed before a call to **srv_sendrow**.</span></span> <span data-ttu-id="7385c-137">O endereço dos dados de origem pode ser alterado entre chamadas para **srv_sendrow**, usando **srv_setcoldata**.</span><span class="sxs-lookup"><span data-stu-id="7385c-137">The source data address can be changed between calls to **srv_sendrow** by using **srv_setcoldata**.</span></span> <span data-ttu-id="7385c-138">A memória alocada para *srcdata* não deve ser liberada até que os dados da coluna sejam substituídos por outra chamada para **srv_setcoldata** ou até que **srv_senddone** seja chamado.</span><span class="sxs-lookup"><span data-stu-id="7385c-138">Memory allocated for *srcdata* should not be freed until the column data is replaced by another call to **srv_setcoldata**, or until **srv_senddone** is called.</span></span>  
  
 <span data-ttu-id="7385c-139">Caso *desttype* seja SRVDECIMAL ou SRVNUMERIC, o parâmetro *srcdata* deverá ser um ponteiro para uma estrutura DBNUMERIC ou DBDECIMAL com os campos de precisão e escala da estrutura já definidos com os valores desejados.</span><span class="sxs-lookup"><span data-stu-id="7385c-139">If *desttype* is SRVDECIMAL or SRVNUMERIC, the *srcdata* parameter must be a pointer to a DBNUMERIC or DBDECIMAL structure with the precision and scale fields of the structure already set to the values you want.</span></span> <span data-ttu-id="7385c-140">É possível usar DEFAULTPRECISION para especificar uma precisão padrão, e DEFAULTSCALE para especificar uma escala padrão.</span><span class="sxs-lookup"><span data-stu-id="7385c-140">You can use DEFAULTPRECISION to specify a default precision, and DEFAULTSCALE to specify a default scale.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="7385c-141">Retornos</span><span class="sxs-lookup"><span data-stu-id="7385c-141">Returns</span></span>  
 <span data-ttu-id="7385c-142">O número da coluna descrita.</span><span class="sxs-lookup"><span data-stu-id="7385c-142">The number of the column described.</span></span> <span data-ttu-id="7385c-143">A primeira coluna é a coluna 1.</span><span class="sxs-lookup"><span data-stu-id="7385c-143">The first column is column 1.</span></span> <span data-ttu-id="7385c-144">Caso ocorra um erro, retorna 0.</span><span class="sxs-lookup"><span data-stu-id="7385c-144">If an error occurs, returns 0.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7385c-145">Comentários</span><span class="sxs-lookup"><span data-stu-id="7385c-145">Remarks</span></span>  
 <span data-ttu-id="7385c-146">A função **srv_describe** deve ser chamada uma vez a cada coluna na linha antes da primeira chamada a **srv_sendrow**.</span><span class="sxs-lookup"><span data-stu-id="7385c-146">The **srv_describe** function must be called once for each column in the row before the first call to **srv_sendrow**.</span></span> <span data-ttu-id="7385c-147">As colunas de uma linha podem ser descritas em qualquer ordem.</span><span class="sxs-lookup"><span data-stu-id="7385c-147">The columns of a row can be described in any order.</span></span>  
  
 <span data-ttu-id="7385c-148">Para alterar o local e o tamanho dos dados de origem nas linhas da coluna antes de o conjunto de resultados completo ser enviado, use **srv_setcoldata** e **srv_setcollen**, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="7385c-148">To change the location and length of the source data in column rows before the complete result set has been sent, use **srv_setcoldata** and **srv_setcollen**, respectively.</span></span>  
  
 <span data-ttu-id="7385c-149">Para obter uma descrição dos tipos de dados e conversões de tipo de dados da API de Procedimento Armazenado Estendido, consulte [Tipos de dados &#40;API de Procedimento Armazenado Estendido&#41;](data-types-extended-stored-procedure-api.md).</span><span class="sxs-lookup"><span data-stu-id="7385c-149">For a description of data types and Extended Store Procedure API data type conversions, see[Data Types &#40;Extended Stored Procedure API&#41;](data-types-extended-stored-procedure-api.md).</span></span>  
  
 <span data-ttu-id="7385c-150">Caso o nome da coluna do aplicativo esteja em Unicode, você precisará convertê-lo na página de código multibyte do servidor antes de chamar **srv_describe**.</span><span class="sxs-lookup"><span data-stu-id="7385c-150">If the column name in your application is in Unicode, you need to convert it to the multibyte code page of the server before calling **srv_describe**.</span></span> <span data-ttu-id="7385c-151">Para obter mais informações, consulte [dados Unicode e páginas de código do servidor](../extended-stored-procedures-programming/unicode-data-and-server-code-pages.md).</span><span class="sxs-lookup"><span data-stu-id="7385c-151">For more information, see [Unicode Data and Server Code Pages](../extended-stored-procedures-programming/unicode-data-and-server-code-pages.md).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="7385c-152">Você deve examinar totalmente o código-fonte de procedimentos armazenados estendidos e deve testar as DLLs compiladas antes de instalá-las em um servidor de produção.</span><span class="sxs-lookup"><span data-stu-id="7385c-152">You should thoroughly review the source code of extended stored procedures, and you should test the compiled DLLs before you install them on a production server.</span></span> <span data-ttu-id="7385c-153">Para obter informações sobre revisão e testes de segurança, consulte este [site da Microsoft](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span><span class="sxs-lookup"><span data-stu-id="7385c-153">For information about security review and testing, see this [Microsoft Web site](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7385c-154">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="7385c-154">See Also</span></span>  
 <span data-ttu-id="7385c-155">[srv_sendrow &#40;API de procedimento armazenado estendido&#41;](srv-sendrow-extended-stored-procedure-api.md) </span><span class="sxs-lookup"><span data-stu-id="7385c-155">[srv_sendrow &#40;Extended Stored Procedure API&#41;](srv-sendrow-extended-stored-procedure-api.md) </span></span>  
 <span data-ttu-id="7385c-156">[srv_setutype &#40;API de procedimento armazenado estendido&#41;](srv-setutype-extended-stored-procedure-api.md) </span><span class="sxs-lookup"><span data-stu-id="7385c-156">[srv_setutype &#40;Extended Stored Procedure API&#41;](srv-setutype-extended-stored-procedure-api.md) </span></span>  
 [<span data-ttu-id="7385c-157">srv_setcoldata &#40;API de Procedimento Armazenado Estendido&#41;</span><span class="sxs-lookup"><span data-stu-id="7385c-157">srv_setcoldata &#40;Extended Stored Procedure API&#41;</span></span>](srv-setcoldata-extended-stored-procedure-api.md)  
  
  
