export PYTHONDONTWRITEBYTECODE=1 &&

source /etc/profile.d/qt6.rc &&

python -m build --wheel --no-isolation &&

prepare_install &&
python -m installer --destdir=/ dist/*.whl
