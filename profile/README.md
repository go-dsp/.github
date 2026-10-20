<p align="center"><img src="https://raw.githubusercontent.com/go-dsp/brand/main/social/go-dsp.png" alt="go-dsp" width="720"></p>

# go-dsp

🌐 **[Website](https://go-dsp.github.io)** · 📚 **[Documentation](https://go-dsp.github.io/docs/)**

**Digital signal processing in pure Go (CGO=0): filter design and filtering, spectral estimation and resampling, with the semantics of SciPy's `scipy.signal`.**

`signal` provides IIR and FIR design (Butterworth, Chebyshev, elliptic, Bessel,
Parks–McClellan, windows), filtering and zero-phase filtering, convolution,
Welch, STFT and Lomb–Scargle spectral estimation, resampling and peak finding.
Its tests replay recorded answers of SciPy 1.18.1, and its documentation
records the maximum error in ULPs and the time against SciPy on one core.
Wavelets and audio I/O are planned in this organisation and not started.

```go
z, _ := signal.Butter(8, []float64{0.2}, signal.Lowpass, nil) // zeros, poles, gain
sos, _ := z.SOS(false)                                        // second-order sections
y, _ := signal.SOSFiltFilt(sos, x, nil)                       // zero-phase filtering
f, p, _ := signal.Welch(x, &signal.SpectralOptions{Fs: 1000, Nperseg: 1024})
```

## Repositories

| Repo | What it is |
|------|------------|
| [**signal**](https://github.com/go-dsp/signal) | released v0.1.0: filter design (IIR, FIR, windows), filtering, convolution, spectral estimation, resampling, peak finding |
| [**docs**](https://github.com/go-dsp/docs) | the documentation site (Hugo + Hextra), served at [/docs/](https://go-dsp.github.io/docs/) |
| [**go-dsp.github.io**](https://github.com/go-dsp/go-dsp.github.io) | the landing page (Hugo) |
| [**brand**](https://github.com/go-dsp/brand) | logo, icons and social images |

`signal` is part of an ecosystem with
[go-fft](https://github.com/go-fft/fft) (transforms and windows),
[go-numerics](https://github.com/go-numerics) (special functions),
[go-simd](https://github.com/go-simd/floats) (the SIMD dot product) and
[go-ndarray](https://github.com/go-ndarray/ndarray) (N-dimensional arrays).
