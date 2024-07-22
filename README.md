# 0D-or-1D-target-tensor-expected-multi-target-not-supported
nn.CrossEntropyLoss() 혹은 F.cross_entropy 를 사용했을 때 자주 발생한다

그럴떈 스퀴즈를 사용하든 뭘해서 shape을 [n,] 이런 형태로 만들어줘야 한다
nn.CrossEntropyLoss()(pred, target.squeeze(dim=-1))


RuntimeError: "nll_loss_forward_reduce_cuda_kernel_2d_index" not implemented for 'Int'
의 경우 데이터를 GPU에 저장하기 전에 대상 유형을 변환하면 됩니다.-> to(device)

label을 LongTensorㅇ로 캐스팅 해주면 됩니다.
targets = targets.type(torch.LongTensor)
