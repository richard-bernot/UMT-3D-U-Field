3D U-Field Simulation

A deterministic, history-dependent 3D scalar lattice simulation used to study emergent regime behavior under local contrast, recursive redistribution, and decoherence.

This notebook is a compact scalar-only 3D lift of the precursor 2D U-Field implementation. It is self-contained and can be run directly in Google Colab. Detailed implementation notes are included as comments throughout the code.

Running the Simulation

Open the .ipynb notebook in Google Colab.

Run the Helper primitives and Compact scalar-only 3D execution path cells.

Run the Signed 3D Rendering cell.

Set the desired parameters in Run Compact 3D Simulation.

Run the simulation cell.

Optionally run Preview Key Frames and MP4 export.

The simulation reports a final validation check and summary of the completed run.

Primary Settings

The main run parameters are defined through ScalarConfig:

nz, ny, nx — lattice dimensions. Dimensions must be odd so the seed sits exactly at the origin.

steps — number of evolved state updates.

w — rolling history window. Values of 3 or greater are supported; the baseline is 6.

alpha — steepness of the activation response.

rho_c — activation midpoint.

u0 — magnitude of the initial central perturbation.

seed_sign — sign of the initial perturbation: 1 or -1.

lambda_delta — weight of the local contrast response.

lambda_flux — weight of recursive redistribution.

lambda_decoherence — weight of decoherence/damping.

Baseline motion-law weights are:

lambda_delta = 1.00
lambda_flux = 0.50
lambda_decoherence = 0.25

A typical full run uses:

nz = 75
ny = 75
nx = 75
steps = 500
w = 6
alpha = 10.0
rho_c = 0.5
u0 = 1e-3
seed_sign = 1

Visualization and Export

The 3D field is rendered as a signed point cloud.

max_points — maximum number of active points rendered.

export_display_percentile — global display scaling for the signed field.

fps — exported video frame rate.

interval_ms — animation interval.

output_mp4 — MP4 filename.

cmap — visualization colormap.

Run Preview Key Frames to inspect the blank, seeded, intermediate, and final states.

Run MP4 export to generate and download the stored U-field evolution as a video.

Note: A simulation step represents resolved state succession within the model and should not be interpreted as a physical unit of clock time.

License

Released under the GNU General Public License v3.0 (GPLv3).
